---
title: JobSteps (objeto del Agente SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- JobSteps object
- SQLAgent:JobSteps
ms.assetid: 44f9983c-1753-4fe0-8475-973aa2460b3a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3759303807714e2bb7f71f59e644bc485d36cfcb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670335"
---
# <a name="sql-server-agent-jobsteps-object"></a><span data-ttu-id="0bd45-102">JobSteps (objeto del Agente SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0bd45-102">SQL Server Agent, JobSteps Object</span></span>
  <span data-ttu-id="0bd45-103">El objeto de rendimiento [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] JobSteps **del Agente** contiene contadores de rendimiento que informan sobre los pasos de trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0bd45-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **JobSteps** performance object contains performance counters that report information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps.</span></span> <span data-ttu-id="0bd45-104">En la siguiente tabla se enumeran los contadores incluidos en este objeto.</span><span class="sxs-lookup"><span data-stu-id="0bd45-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="0bd45-105">La siguiente tabla contiene los contadores de **SQLAgent:JobSteps** .</span><span class="sxs-lookup"><span data-stu-id="0bd45-105">The table below contains the **SQLAgent:JobSteps** counters.</span></span>  
  
|<span data-ttu-id="0bd45-106">Nombre</span><span class="sxs-lookup"><span data-stu-id="0bd45-106">Name</span></span>|<span data-ttu-id="0bd45-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bd45-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="0bd45-108">**Pasos activos**</span><span class="sxs-lookup"><span data-stu-id="0bd45-108">**Active steps**</span></span>|<span data-ttu-id="0bd45-109">Este contador muestra el número de pasos de trabajo que se están ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="0bd45-109">This counter reports the number of job steps currently running.</span></span>|  
|<span data-ttu-id="0bd45-110">**Pasos en cola**</span><span class="sxs-lookup"><span data-stu-id="0bd45-110">**Queued steps**</span></span>|<span data-ttu-id="0bd45-111">Este contador informa acerca del número de pasos de trabajo preparados para que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] los ejecute, pero cuya ejecución aún no se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="0bd45-111">This counter reports the number of job steps that are ready for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to run, but which have not yet started running.</span></span>|  
|<span data-ttu-id="0bd45-112">**Total de reintentos de pasos**</span><span class="sxs-lookup"><span data-stu-id="0bd45-112">**Total step retries**</span></span>|<span data-ttu-id="0bd45-113">Este contador informa del número total de veces que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha reintentado un paso de trabajo desde el último reinicio del servidor.</span><span class="sxs-lookup"><span data-stu-id="0bd45-113">This counter reports the total number of times that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has retried a job step since the last server restart.</span></span>|  
  
 <span data-ttu-id="0bd45-114">Cada contador del objeto contiene las instancias siguientes:</span><span class="sxs-lookup"><span data-stu-id="0bd45-114">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="0bd45-115">Instancia</span><span class="sxs-lookup"><span data-stu-id="0bd45-115">Instance</span></span>|<span data-ttu-id="0bd45-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bd45-116">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="0bd45-117">**_Total**</span><span class="sxs-lookup"><span data-stu-id="0bd45-117">**_Total**</span></span>|<span data-ttu-id="0bd45-118">Información de todos los pasos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0bd45-118">Information for all job steps.</span></span>|  
|<span data-ttu-id="0bd45-119">**ActiveScripting**</span><span class="sxs-lookup"><span data-stu-id="0bd45-119">**ActiveScripting**</span></span>|<span data-ttu-id="0bd45-120">Información de los pasos de trabajo que utilizan el subsistema **ActiveScripting** .</span><span class="sxs-lookup"><span data-stu-id="0bd45-120">Information for job steps that use the **ActiveScripting** subsystem.</span></span>|  
|<span data-ttu-id="0bd45-121">**ANALYSISCOMMAND**</span><span class="sxs-lookup"><span data-stu-id="0bd45-121">**ANALYSISCOMMAND**</span></span>|<span data-ttu-id="0bd45-122">Información de los pasos de trabajo que utilizan el subsistema ANALYSISCOMMAND.</span><span class="sxs-lookup"><span data-stu-id="0bd45-122">Information for job steps that use the ANALYSISCOMMAND subsystem.</span></span>|  
|<span data-ttu-id="0bd45-123">**ANALYSISQUERY**</span><span class="sxs-lookup"><span data-stu-id="0bd45-123">**ANALYSISQUERY**</span></span>|<span data-ttu-id="0bd45-124">Información de los pasos de trabajo que utilizan el subsistema ANALYSISQUERY.</span><span class="sxs-lookup"><span data-stu-id="0bd45-124">Information for job steps that use the ANALYSISQUERY subsystem.</span></span>|  
|<span data-ttu-id="0bd45-125">**CmdExec**</span><span class="sxs-lookup"><span data-stu-id="0bd45-125">**CmdExec**</span></span>|<span data-ttu-id="0bd45-126">Información de los pasos de trabajo que utilizan el subsistema **CmdExec** .</span><span class="sxs-lookup"><span data-stu-id="0bd45-126">Information for job steps that use the **CmdExec** subsystem.</span></span>|  
|<span data-ttu-id="0bd45-127">**Distribución**</span><span class="sxs-lookup"><span data-stu-id="0bd45-127">**Distribution**</span></span>|<span data-ttu-id="0bd45-128">Información de los pasos de trabajo que utilizan el subsistema **Distribution** .</span><span class="sxs-lookup"><span data-stu-id="0bd45-128">Information for job steps that use the **Distribution** subsystem.</span></span>|  
|<span data-ttu-id="0bd45-129">**Dts**</span><span class="sxs-lookup"><span data-stu-id="0bd45-129">**Dts**</span></span>|<span data-ttu-id="0bd45-130">Información de los pasos de trabajo que utilizan el subsistema [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0bd45-130">Information for job steps that use the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] subsystem.</span></span>|  
|<span data-ttu-id="0bd45-131">**LogReader**</span><span class="sxs-lookup"><span data-stu-id="0bd45-131">**LogReader**</span></span>|<span data-ttu-id="0bd45-132">Información de los pasos de trabajo que utilizan el subsistema **LogReader** .</span><span class="sxs-lookup"><span data-stu-id="0bd45-132">Information for job steps that use the **LogReader** subsystem.</span></span>|  
|<span data-ttu-id="0bd45-133">**Combinar**</span><span class="sxs-lookup"><span data-stu-id="0bd45-133">**Merge**</span></span>|<span data-ttu-id="0bd45-134">Información de los pasos de trabajo que utilizan el subsistema **Merge** .</span><span class="sxs-lookup"><span data-stu-id="0bd45-134">Information for job steps that use the **Merge** subsystem.</span></span>|  
|<span data-ttu-id="0bd45-135">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0bd45-135">**PowerShell**</span></span>|<span data-ttu-id="0bd45-136">Información de los pasos de trabajo que utilizan el subsistema **PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="0bd45-136">Information for job steps that use the **PowerShell** subsystem.</span></span>|  
|<span data-ttu-id="0bd45-137">**QueueReader**</span><span class="sxs-lookup"><span data-stu-id="0bd45-137">**QueueReader**</span></span>|<span data-ttu-id="0bd45-138">Información de los pasos de trabajo que utilizan el subsistema **QueueReader** .</span><span class="sxs-lookup"><span data-stu-id="0bd45-138">Information for job steps that use the **QueueReader** subsystem.</span></span>|  
|<span data-ttu-id="0bd45-139">**Instantánea**</span><span class="sxs-lookup"><span data-stu-id="0bd45-139">**Snapshot**</span></span>|<span data-ttu-id="0bd45-140">Información de los pasos de trabajo que utilizan el subsistema **Snapshot** .</span><span class="sxs-lookup"><span data-stu-id="0bd45-140">Information for job steps that use the **Snapshot** subsystem.</span></span>|  
|<span data-ttu-id="0bd45-141">**TSQL**</span><span class="sxs-lookup"><span data-stu-id="0bd45-141">**TSQL**</span></span>|<span data-ttu-id="0bd45-142">Información de los pasos de trabajo que ejecutan [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bd45-142">Information for job steps that execute [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0bd45-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0bd45-143">See Also</span></span>  
 <span data-ttu-id="0bd45-144">[Administrar pasos de trabajo](../../ssms/agent/manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="0bd45-144">[Manage Job Steps](../../ssms/agent/manage-job-steps.md) </span></span>  
 <span data-ttu-id="0bd45-145">[Usar objetos de rendimiento](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="0bd45-145">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="0bd45-146">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="0bd45-146">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
