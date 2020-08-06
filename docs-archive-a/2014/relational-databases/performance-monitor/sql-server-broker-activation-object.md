---
title: Broker Activation (objeto de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Broker Activation
- Broker Activation object
ms.assetid: cd9b6880-c924-42c7-b333-09c303317c0b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4048c2baecaeb4bde7a1e215a15e8c51a60a01bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745735"
---
# <a name="sql-server-broker-activation-object"></a><span data-ttu-id="27feb-102">Broker Activation (objeto de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="27feb-102">SQL Server, Broker Activation Object</span></span>
  <span data-ttu-id="27feb-103">El objeto de rendimiento **SQLServer:BrokerActivation** incluye contadores de rendimiento que aportan información acerca de la activación de procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="27feb-103">The **SQLServer:BrokerActivation** performance object contains performance counters that report information on stored procedure activation.</span></span> <span data-ttu-id="27feb-104">En la siguiente tabla se enumeran los contadores incluidos en este objeto.</span><span class="sxs-lookup"><span data-stu-id="27feb-104">The table below lists the counters that this object contains.</span></span>  
  
|<span data-ttu-id="27feb-105">Contadores de Broker Activation de SQL Server</span><span class="sxs-lookup"><span data-stu-id="27feb-105">SQL Server Broker Activation counters</span></span>|<span data-ttu-id="27feb-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="27feb-106">Description</span></span>|  
|-------------------------------------------|-----------------|  
|<span data-ttu-id="27feb-107">**Procedimientos almacenados invocados/seg.**</span><span class="sxs-lookup"><span data-stu-id="27feb-107">**Stored Procedures Invoked/sec**</span></span>|<span data-ttu-id="27feb-108">Este contador informa del número total de procedimientos de activación almacenados que han invocado todos los monitores de cola en la instancia por segundo.</span><span class="sxs-lookup"><span data-stu-id="27feb-108">This counter reports the total number of activation stored procedures invoked by all queue monitors in the instance per second.</span></span>|  
|<span data-ttu-id="27feb-109">**Límite de tareas alcanzado**</span><span class="sxs-lookup"><span data-stu-id="27feb-109">**Task Limit Reached**</span></span>|<span data-ttu-id="27feb-110">Este contador informa del número total de veces que un monitor de cola habría iniciado una tarea y no lo hizo porque ya se estaba ejecutando el máximo de tareas de la cola.</span><span class="sxs-lookup"><span data-stu-id="27feb-110">This counter reports the total number of times that a queue monitor would have started a new task, but did not because the maximum number of tasks for the queue is already running.</span></span>|  
|<span data-ttu-id="27feb-111">**Límite de tareas alcanzado/seg.**</span><span class="sxs-lookup"><span data-stu-id="27feb-111">**Task Limit Reached/sec**</span></span>|<span data-ttu-id="27feb-112">Este contador informa del número de veces por segundo que un monitor de cola habría iniciado una tarea y no lo hizo porque ya se estaba ejecutando el máximo de tareas de la cola.</span><span class="sxs-lookup"><span data-stu-id="27feb-112">This counter reports the number of times per second that a queue monitor would have started a new task, but did not because the maximum number of tasks for the queue is already running.</span></span>|  
|<span data-ttu-id="27feb-113">**Tareas anuladas/seg.**</span><span class="sxs-lookup"><span data-stu-id="27feb-113">**Tasks Aborted/sec**</span></span>|<span data-ttu-id="27feb-114">Este contador informa del número de tareas de procedimiento almacenado de activación que finalizan con un error o que un monitor de cola anula porque no recibe mensajes.</span><span class="sxs-lookup"><span data-stu-id="27feb-114">This counter reports the number of activation stored procedure tasks that end with an error, or are aborted by a queue monitor for failing to receive messages.</span></span>|  
|<span data-ttu-id="27feb-115">**Tareas en ejecución**</span><span class="sxs-lookup"><span data-stu-id="27feb-115">**Tasks Running**</span></span>|<span data-ttu-id="27feb-116">Este contador informa del número de procedimientos almacenados de activación que se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="27feb-116">This counter reports the number of activation stored procedures that are currently running.</span></span>|  
|<span data-ttu-id="27feb-117">**Tareas iniciadas/seg.**</span><span class="sxs-lookup"><span data-stu-id="27feb-117">**Tasks Started/sec**</span></span>|<span data-ttu-id="27feb-118">Este contador informa del número de procedimientos de activación almacenados que han iniciado por segundo todos los monitores de cola en la instancia.</span><span class="sxs-lookup"><span data-stu-id="27feb-118">This counter reports the number of activation stored procedures started per second by all queue monitors in the instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27feb-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27feb-119">See Also</span></span>  
 <span data-ttu-id="27feb-120">[sys.dm_broker_activated_tasks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-activated-tasks-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="27feb-120">[sys.dm_broker_activated_tasks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-activated-tasks-transact-sql) </span></span>  
 <span data-ttu-id="27feb-121">[sys.dm_broker_queue_monitors &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-queue-monitors-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="27feb-121">[sys.dm_broker_queue_monitors &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-queue-monitors-transact-sql) </span></span>  
 [<span data-ttu-id="27feb-122">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="27feb-122">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
