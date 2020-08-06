---
title: MSSQL_ENG014150 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014150 error
ms.assetid: c3dd3109-abf3-4b38-a4e9-ef48d0235656
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c926d05be9613ff559f119484fa5e238d71d861
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662828"
---
# <a name="mssql_eng014150"></a><span data-ttu-id="735a9-102">MSSQL_ENG014150</span><span class="sxs-lookup"><span data-stu-id="735a9-102">MSSQL_ENG014150</span></span>
    
## <a name="message-details"></a><span data-ttu-id="735a9-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="735a9-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="735a9-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="735a9-104">Product Name</span></span>|<span data-ttu-id="735a9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="735a9-105">SQL Server</span></span>|  
|<span data-ttu-id="735a9-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="735a9-106">Event ID</span></span>|<span data-ttu-id="735a9-107">14150</span><span class="sxs-lookup"><span data-stu-id="735a9-107">14150</span></span>|  
|<span data-ttu-id="735a9-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="735a9-108">Event Source</span></span>|<span data-ttu-id="735a9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="735a9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="735a9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="735a9-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="735a9-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="735a9-111">Symbolic Name</span></span>||  
|<span data-ttu-id="735a9-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="735a9-112">Message Text</span></span>|<span data-ttu-id="735a9-113">Replicación-%s: el agente %s se ejecutó correctamente.</span><span class="sxs-lookup"><span data-stu-id="735a9-113">Replication-%s: agent %s succeeded.</span></span> <span data-ttu-id="735a9-114">%s</span><span class="sxs-lookup"><span data-stu-id="735a9-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="735a9-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="735a9-115">Explanation</span></span>  
 <span data-ttu-id="735a9-116">Este mensaje indica que un agente de replicación ha finalizado la ejecución correctamente.</span><span class="sxs-lookup"><span data-stu-id="735a9-116">This message indicates that a replication agent has successfully finished running.</span></span> <span data-ttu-id="735a9-117">La replicación usa los siguientes agentes:</span><span class="sxs-lookup"><span data-stu-id="735a9-117">Replication uses the following agents:</span></span>  
  
-   <span data-ttu-id="735a9-118">Agente de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="735a9-118">The Snapshot Agent.</span></span> <span data-ttu-id="735a9-119">Todas las publicaciones usan este agente.</span><span class="sxs-lookup"><span data-stu-id="735a9-119">This agent is used by all publications.</span></span>  
  
-   <span data-ttu-id="735a9-120">Agente de registro del LOG.</span><span class="sxs-lookup"><span data-stu-id="735a9-120">The Log Reader Agent.</span></span> <span data-ttu-id="735a9-121">Todas las publicaciones transaccionales usan este agente.</span><span class="sxs-lookup"><span data-stu-id="735a9-121">This agent is used by all transactional publications.</span></span>  
  
-   <span data-ttu-id="735a9-122">Agente de lectura de cola.</span><span class="sxs-lookup"><span data-stu-id="735a9-122">The Queue Reader Agent.</span></span> <span data-ttu-id="735a9-123">Todas las publicaciones transaccionales habilitadas para las suscripciones de actualización en cola usan este agente.</span><span class="sxs-lookup"><span data-stu-id="735a9-123">This agent is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="735a9-124">Agente de distribución.</span><span class="sxs-lookup"><span data-stu-id="735a9-124">The Distribution Agent.</span></span> <span data-ttu-id="735a9-125">Este agente sincroniza las suscripciones a publicaciones transaccionales y publicaciones de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="735a9-125">This agent synchronizes subscriptions to transactional and snapshot publications.</span></span>  
  
-   <span data-ttu-id="735a9-126">Agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="735a9-126">The Merge Agent.</span></span> <span data-ttu-id="735a9-127">Este agente sincroniza las suscripciones a publicaciones de combinación.</span><span class="sxs-lookup"><span data-stu-id="735a9-127">This agent synchronizes subscriptions to merge publications.</span></span>  
  
-   <span data-ttu-id="735a9-128">Trabajos de mantenimiento de la replicación.</span><span class="sxs-lookup"><span data-stu-id="735a9-128">Replication maintenance jobs.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="735a9-129">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="735a9-129">User Action</span></span>  
 <span data-ttu-id="735a9-130">El Agente de registro del LOG, el Agente de lectura de cola y el Agente de distribución se ejecutan normalmente de forma continua, mientras que el resto de agentes se ejecutan normalmente a petición o en función de una programación.</span><span class="sxs-lookup"><span data-stu-id="735a9-130">The Log Reader Agent, Queue Reader Agent, and Distribution Agent typically run continuously, whereas the other agents typically run on demand or on a schedule.</span></span> <span data-ttu-id="735a9-131">Si no espera que un agente haya completado una ejecución, compruebe el estado del agente.</span><span class="sxs-lookup"><span data-stu-id="735a9-131">If you do not expect an agent to have completed a run, check the status of the agent.</span></span> <span data-ttu-id="735a9-132">Para más información, consulte [Monitor Replication Agents](agents/replication-agents-overview.md).</span><span class="sxs-lookup"><span data-stu-id="735a9-132">For more information, see [Monitor Replication Agents](agents/replication-agents-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="735a9-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="735a9-133">See Also</span></span>  
 <span data-ttu-id="735a9-134">[Administración del Agente de replicación](agents/replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="735a9-134">[Replication Agent Administration](agents/replication-agent-administration.md) </span></span>  
 <span data-ttu-id="735a9-135">[Referencia de errores y eventos &#40;replicación&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="735a9-135">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="735a9-136">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="735a9-136">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="735a9-137">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="735a9-137">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="735a9-138">[Replication Merge Agent](agents/replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="735a9-138">[Replication Merge Agent](agents/replication-merge-agent.md) </span></span>  
 <span data-ttu-id="735a9-139">[Agente de lectura de cola de replicación](agents/replication-queue-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="735a9-139">[Replication Queue Reader Agent](agents/replication-queue-reader-agent.md) </span></span>  
 [<span data-ttu-id="735a9-140">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="735a9-140">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
  
