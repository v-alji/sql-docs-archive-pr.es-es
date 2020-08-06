---
title: Editor de la tarea transferir trabajos (página trabajos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferjobstask.jobs.f1
helpviewer_keywords:
- Transfer Jobs Task Editor
ms.assetid: e72b1dc7-8cda-4ee6-abb5-d438370f04df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d2d506da6997965e40d66521f7dccb8218e165fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678247"
---
# <a name="transfer-jobs-task-editor-jobs-page"></a><span data-ttu-id="034a0-102">Editor de la tarea Transferir trabajos (página Trabajos)</span><span class="sxs-lookup"><span data-stu-id="034a0-102">Transfer Jobs Task Editor (Jobs Page)</span></span>
  <span data-ttu-id="034a0-103">Utilice la página **Trabajos** del cuadro de diálogo **Editor de la tarea Transferir trabajos** para especificar las propiedades de copia de una o más tareas del Agente de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] de una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a otra.</span><span class="sxs-lookup"><span data-stu-id="034a0-103">Use the **Jobs** page of the **Transfer Jobs Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="034a0-104">Para obtener más información acerca de la tarea Transferir trabajos, vea [Transfer Jobs Task](control-flow/transfer-jobs-task.md).</span><span class="sxs-lookup"><span data-stu-id="034a0-104">For more information about the Transfer Jobs task, see [Transfer Jobs Task](control-flow/transfer-jobs-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="034a0-105">Para tener acceso a trabajos del servidor de origen, los usuarios deben ser miembros de al menos el rol fijo de base de datos **SQLAgentUserRole** en el servidor.</span><span class="sxs-lookup"><span data-stu-id="034a0-105">To access jobs on the source server, users must be a member of at least the **SQLAgentUserRole** fixed database role on the server.</span></span> <span data-ttu-id="034a0-106">Para crear trabajos correctamente en el servidor de destino, el usuario debe ser miembro del rol fijo de servidor **sysadmin** o una de los roles fijos de base de datos del Agente de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="034a0-106">To successfully create jobs on the destination server, the user must be a member of the **sysadmin** fixed server role or one of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles.</span></span> <span data-ttu-id="034a0-107">Para obtener más información sobre los roles fijos de base de datos del Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y sus permisos, vea [Roles fijos de base de datos del Agente SQL Server](../ssms/agent/sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="034a0-107">For more information about [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles and their permissions, see [SQL Server Agent Fixed Database Roles](../ssms/agent/sql-server-agent-fixed-database-roles.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="034a0-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="034a0-108">Options</span></span>  
 <span data-ttu-id="034a0-109">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="034a0-109">**SourceConnection**</span></span>  
 <span data-ttu-id="034a0-110">Seleccione un administrador de conexiones SMO de la lista o haga clic en **\<New connection...>** para crear una nueva conexión al servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="034a0-110">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="034a0-111">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="034a0-111">**DestinationConnection**</span></span>  
 <span data-ttu-id="034a0-112">Seleccione un administrador de conexiones SMO de la lista o haga clic en **\<New connection...>** para crear una nueva conexión al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="034a0-112">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="034a0-113">**TransferAllJobs**</span><span class="sxs-lookup"><span data-stu-id="034a0-113">**TransferAllJobs**</span></span>  
 <span data-ttu-id="034a0-114">Seleccione si la tarea debe copiar todos los trabajos del Agente de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o solo los trabajos especificados del origen al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="034a0-114">Select whether the task should copy all or only the specified [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs from the source to the destination server.</span></span>  
  
 <span data-ttu-id="034a0-115">Esta propiedad presenta las opciones indicadas en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="034a0-115">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="034a0-116">Value</span><span class="sxs-lookup"><span data-stu-id="034a0-116">Value</span></span>|<span data-ttu-id="034a0-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="034a0-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="034a0-118">**True**</span><span class="sxs-lookup"><span data-stu-id="034a0-118">**True**</span></span>|<span data-ttu-id="034a0-119">Copia todos los trabajos.</span><span class="sxs-lookup"><span data-stu-id="034a0-119">Copy all jobs.</span></span>|  
|<span data-ttu-id="034a0-120">**False**</span><span class="sxs-lookup"><span data-stu-id="034a0-120">**False**</span></span>|<span data-ttu-id="034a0-121">Copia solo los trabajos especificados.</span><span class="sxs-lookup"><span data-stu-id="034a0-121">Copy only the specified jobs.</span></span>|  
  
 <span data-ttu-id="034a0-122">**JobsList**</span><span class="sxs-lookup"><span data-stu-id="034a0-122">**JobsList**</span></span>  
 <span data-ttu-id="034a0-123">Haga clic en el botón Examinar **(…)** para seleccionar los trabajos que quiere copiar.</span><span class="sxs-lookup"><span data-stu-id="034a0-123">Click the browse button **(...)** to select the jobs to copy.</span></span> <span data-ttu-id="034a0-124">Se debe seleccionar al menos un trabajo.</span><span class="sxs-lookup"><span data-stu-id="034a0-124">At least one job must be selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="034a0-125">Especifique **SourceConnection** antes de seleccionar los trabajos que quiere copiar.</span><span class="sxs-lookup"><span data-stu-id="034a0-125">Specify the **SourceConnection** before selecting jobs to copy.</span></span>  
  
 <span data-ttu-id="034a0-126">La opción **JobsList** no está disponible cuando **TransferAllJobs** se establece como **True**.</span><span class="sxs-lookup"><span data-stu-id="034a0-126">The **JobsList** option is unavailable when **TransferAllJobs** is set to **True**.</span></span>  
  
 <span data-ttu-id="034a0-127">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="034a0-127">**IfObjectExists**</span></span>  
 <span data-ttu-id="034a0-128">Seleccione cómo debería controlar la tarea los trabajos con el mismo nombre que ya existen en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="034a0-128">Select how the task should handle jobs of the same name that already exist on the destination server.</span></span>  
  
 <span data-ttu-id="034a0-129">Esta propiedad presenta las opciones indicadas en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="034a0-129">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="034a0-130">Value</span><span class="sxs-lookup"><span data-stu-id="034a0-130">Value</span></span>|<span data-ttu-id="034a0-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="034a0-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="034a0-132">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="034a0-132">**FailTask**</span></span>|<span data-ttu-id="034a0-133">La tarea falla si ya existen trabajos con el mismo nombre en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="034a0-133">Task fails if jobs of the same name already exist on the destination server.</span></span>|  
|<span data-ttu-id="034a0-134">**Sobrescribir**</span><span class="sxs-lookup"><span data-stu-id="034a0-134">**Overwrite**</span></span>|<span data-ttu-id="034a0-135">La tarea sobrescribe los trabajos con el mismo nombre en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="034a0-135">Task overwrites jobs of the same name on the destination server.</span></span>|  
|<span data-ttu-id="034a0-136">**Skip**</span><span class="sxs-lookup"><span data-stu-id="034a0-136">**Skip**</span></span>|<span data-ttu-id="034a0-137">La tarea omite los trabajos con el mismo nombre que existen en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="034a0-137">Task skips jobs of the same name that exist on the destination server.</span></span>|  
  
 <span data-ttu-id="034a0-138">**EnableJobsAtDestination**</span><span class="sxs-lookup"><span data-stu-id="034a0-138">**EnableJobsAtDestination**</span></span>  
 <span data-ttu-id="034a0-139">Seleccione si se deben habilitar los trabajos copiados en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="034a0-139">Select whether the jobs copied to the destination server should be enabled.</span></span>  
  
 <span data-ttu-id="034a0-140">Esta propiedad presenta las opciones indicadas en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="034a0-140">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="034a0-141">Value</span><span class="sxs-lookup"><span data-stu-id="034a0-141">Value</span></span>|<span data-ttu-id="034a0-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="034a0-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="034a0-143">**True**</span><span class="sxs-lookup"><span data-stu-id="034a0-143">**True**</span></span>|<span data-ttu-id="034a0-144">Habilita los trabajos en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="034a0-144">Enable jobs on destination server.</span></span>|  
|<span data-ttu-id="034a0-145">**False**</span><span class="sxs-lookup"><span data-stu-id="034a0-145">**False**</span></span>|<span data-ttu-id="034a0-146">Deshabilita los trabajos en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="034a0-146">Disable jobs on destination server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="034a0-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="034a0-147">See Also</span></span>  
 <span data-ttu-id="034a0-148">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="034a0-148">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="034a0-149">[Tareas de Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="034a0-149">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="034a0-150">[Editor de la tarea transferir trabajos &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="034a0-150">[Transfer Jobs Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="034a0-151">[Página Expresiones](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="034a0-151">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="034a0-152">Administrador de conexiones SMO</span><span class="sxs-lookup"><span data-stu-id="034a0-152">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
