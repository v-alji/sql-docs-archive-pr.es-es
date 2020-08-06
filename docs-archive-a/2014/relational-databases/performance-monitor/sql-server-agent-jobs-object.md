---
title: Jobs (objeto del Agente SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLAgent:Jobs
- Jobs object
ms.assetid: 225b5e2d-4a78-4178-b2b6-b419df83c4aa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 82ee57eba20d44c08eadc125e9dfd69e73c35751
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670336"
---
# <a name="sql-server-agent-jobs-object"></a><span data-ttu-id="52e8b-102">Jobs (objeto del Agente SQL Server)</span><span class="sxs-lookup"><span data-stu-id="52e8b-102">SQL Server Agent, Jobs Object</span></span>
  <span data-ttu-id="52e8b-103">El objeto de rendimiento **Jobs** del Agente SQL Server contiene contadores de rendimiento que proporcionan información acerca de los trabajos del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="52e8b-103">The SQL Server Agent **Jobs** performance object contains performance counters that report information about SQL Server Agent jobs.</span></span> <span data-ttu-id="52e8b-104">En la siguiente tabla se enumeran los contadores incluidos en este objeto.</span><span class="sxs-lookup"><span data-stu-id="52e8b-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="52e8b-105">La tabla siguiente contiene los contadores de **SQLAgent:Jobs** .</span><span class="sxs-lookup"><span data-stu-id="52e8b-105">The table below contains the **SQLAgent:Jobs** counters.</span></span>  
  
|<span data-ttu-id="52e8b-106">Nombre</span><span class="sxs-lookup"><span data-stu-id="52e8b-106">Name</span></span>|<span data-ttu-id="52e8b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="52e8b-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="52e8b-108">**Trabajos activos**</span><span class="sxs-lookup"><span data-stu-id="52e8b-108">**Active Jobs**</span></span>|<span data-ttu-id="52e8b-109">Este contador muestra el número de trabajos que se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="52e8b-109">This counter reports the number of jobs currently running.</span></span>|  
|<span data-ttu-id="52e8b-110">**Trabajos con error**</span><span class="sxs-lookup"><span data-stu-id="52e8b-110">**Failed jobs**</span></span>|<span data-ttu-id="52e8b-111">Este contador muestra el número de trabajos que han terminado con un error.</span><span class="sxs-lookup"><span data-stu-id="52e8b-111">This counter reports the number of jobs that exited with failure.</span></span>|  
|<span data-ttu-id="52e8b-112">**Tasa de trabajos con éxito**</span><span class="sxs-lookup"><span data-stu-id="52e8b-112">**Job success rate**</span></span>|<span data-ttu-id="52e8b-113">Este contador muestra el porcentaje de trabajos ejecutados que se han completado con éxito.</span><span class="sxs-lookup"><span data-stu-id="52e8b-113">This counter reports the percentage of executed jobs that completed successfully.</span></span>|  
|<span data-ttu-id="52e8b-114">**Trabajos activados/minuto**</span><span class="sxs-lookup"><span data-stu-id="52e8b-114">**Jobs activated/minute**</span></span>|<span data-ttu-id="52e8b-115">Este contador muestra el número de trabajos que se han iniciado en el último minuto.</span><span class="sxs-lookup"><span data-stu-id="52e8b-115">This counter reports the number of jobs launched within the last minute.</span></span>|  
|<span data-ttu-id="52e8b-116">**Trabajos en cola**</span><span class="sxs-lookup"><span data-stu-id="52e8b-116">**Queued jobs**</span></span>|<span data-ttu-id="52e8b-117">Este contador muestra el número de trabajos preparados para que el Agente SQL Server pueda ejecutarlos, pero que aún no se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="52e8b-117">This counter reports the number of jobs that are ready for SQL Server Agent to run, but which have not yet started running.</span></span>|  
|<span data-ttu-id="52e8b-118">**Trabajos con éxito**</span><span class="sxs-lookup"><span data-stu-id="52e8b-118">**Successful jobs**</span></span>|<span data-ttu-id="52e8b-119">Este contador muestra el número de trabajos que han terminado con éxito.</span><span class="sxs-lookup"><span data-stu-id="52e8b-119">This counter reports the number of jobs that exited with success.</span></span>|  
  
 <span data-ttu-id="52e8b-120">Cada contador del objeto contiene las instancias siguientes:</span><span class="sxs-lookup"><span data-stu-id="52e8b-120">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="52e8b-121">Instancia</span><span class="sxs-lookup"><span data-stu-id="52e8b-121">Instance</span></span>|<span data-ttu-id="52e8b-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="52e8b-122">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="52e8b-123">**_Total**</span><span class="sxs-lookup"><span data-stu-id="52e8b-123">**_Total**</span></span>|<span data-ttu-id="52e8b-124">Información para todos los trabajos.</span><span class="sxs-lookup"><span data-stu-id="52e8b-124">Information for all jobs.</span></span>|  
|<span data-ttu-id="52e8b-125">**Alertas**</span><span class="sxs-lookup"><span data-stu-id="52e8b-125">**Alerts**</span></span>|<span data-ttu-id="52e8b-126">Información de los trabajos iniciados por las alertas.</span><span class="sxs-lookup"><span data-stu-id="52e8b-126">Information for jobs started by alerts.</span></span>|  
|<span data-ttu-id="52e8b-127">**Otros**</span><span class="sxs-lookup"><span data-stu-id="52e8b-127">**Others**</span></span>|<span data-ttu-id="52e8b-128">Información de los trabajos no iniciados por alertas ni programaciones.</span><span class="sxs-lookup"><span data-stu-id="52e8b-128">Information for jobs that were not started by alerts or schedules.</span></span> <span data-ttu-id="52e8b-129">Normalmente estos trabajos de inician de forma manual mediante **sp_start_job**.</span><span class="sxs-lookup"><span data-stu-id="52e8b-129">Typically these are jobs started manually using **sp_start_job**.</span></span>|  
|<span data-ttu-id="52e8b-130">**Programaciones**</span><span class="sxs-lookup"><span data-stu-id="52e8b-130">**Schedules**</span></span>|<span data-ttu-id="52e8b-131">Información de los trabajos iniciados por las programaciones.</span><span class="sxs-lookup"><span data-stu-id="52e8b-131">Information for jobs started by schedules.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52e8b-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52e8b-132">See Also</span></span>  
 <span data-ttu-id="52e8b-133">[Implementar trabajos](../../ssms/agent/implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="52e8b-133">[Implement Jobs](../../ssms/agent/implement-jobs.md) </span></span>  
 <span data-ttu-id="52e8b-134">[Usar objetos de rendimiento](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="52e8b-134">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="52e8b-135">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="52e8b-135">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
