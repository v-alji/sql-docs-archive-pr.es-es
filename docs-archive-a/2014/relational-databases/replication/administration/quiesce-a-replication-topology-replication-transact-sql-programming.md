---
title: Puesta en modo inactivo de una topología de replicación (programación de la replicación con Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- administering replication, quiescing
- quiesce [SQL Server replication]
- transactional replication, backup and restore
ms.assetid: 7626d575-9994-47be-b772-5b6f1b7ef7ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f12f0fb8ee3a6118e03799d17836573fb5c733df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748079"
---
# <a name="quiesce-a-replication-topology-replication-transact-sql-programming"></a><span data-ttu-id="e9ddb-102">Poner en modo inactivo una topología de replicación (programación de la replicación con Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e9ddb-102">Quiesce a Replication Topology (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="e9ddb-103">*Detener* un sistema implica detener la actividad de las tablas publicadas en todos los nodos y asegurarse de que cada nodo ha recibido todos los cambios de los demás nodos.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-103">*Quiescing* a system involves stopping activity on published tables at all nodes and ensuring that each node has received all changes from all other nodes.</span></span> <span data-ttu-id="e9ddb-104">Este tema explica cómo detener una topología de replicación, una operación necesaria para varias tareas administrativas, y cómo asegurarse que un nodo ha recibido todos los cambios de otros nodos.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-104">This topic explains how to quiesce a replication topology, which is required for a number of administrative tasks, and how to ensure that a node has received all changes from other nodes.</span></span>  
  
### <a name="to-quiesce-a-transactional-replication-topology-with-read-only-subscriptions"></a><span data-ttu-id="e9ddb-105">Para detener una topología de replicación transaccional con suscripciones de solo lectura</span><span class="sxs-lookup"><span data-stu-id="e9ddb-105">To quiesce a transactional replication topology with read-only subscriptions</span></span>  
  
1.  <span data-ttu-id="e9ddb-106">Detenga la actividad en todas las tablas en el publicador.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-106">Stop activity on all published tables at the Publisher.</span></span>  
  
2.  <span data-ttu-id="e9ddb-107">En la base de datos de publicación del publicador, ejecute [sp_posttracertoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9ddb-107">At the Publisher on the publication database, execute [sp_posttracertoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span></span>  
  
3.  <span data-ttu-id="e9ddb-108">En la base de datos de publicación del publicador, ejecute [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9ddb-108">At the Publisher on the publication database, execute [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span></span>  
  
4.  <span data-ttu-id="e9ddb-109">Asegúrese de que cada suscriptor ha recibido el token de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-109">Ensure that each Subscriber has received the tracer token.</span></span>  
  
### <a name="to-quiesce-a-transactional-replication-topology-with-updatable-subscriptions"></a><span data-ttu-id="e9ddb-110">Para detener una topología de replicación transaccional con suscripciones actualizables</span><span class="sxs-lookup"><span data-stu-id="e9ddb-110">To quiesce a transactional replication topology with updatable subscriptions</span></span>  
  
1.  <span data-ttu-id="e9ddb-111">Detenga la actividad en todas las tablas en el publicador y todos los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-111">Stop activity on all published tables at the Publisher and all Subscribers.</span></span>  
  
2.  <span data-ttu-id="e9ddb-112">Si algún suscriptor utiliza suscripciones de actualización en cola:</span><span class="sxs-lookup"><span data-stu-id="e9ddb-112">If any Subscribers use queued updating subscriptions:</span></span>  
  
    1.  <span data-ttu-id="e9ddb-113">Si el Agente de lectura de cola no se está ejecutando de forma continua, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-113">If the Queue Reader Agent is not running in continuous mode, run the agent.</span></span> <span data-ttu-id="e9ddb-114">Para obtener más información sobre la ejecución de agentes, vea [Conceptos de los ejecutables del Agente de replicación](../concepts/replication-agent-executables-concepts.md) o [Iniciar y detener un agente de replicación &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e9ddb-114">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
    2.  <span data-ttu-id="e9ddb-115">Para comprobar que la cola está vacía, ejecute [sp_replqueuemonitor](/sql/relational-databases/system-stored-procedures/sp-replqueuemonitor-transact-sql) en cada suscriptor.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-115">To verify that the queue is empty, execute [sp_replqueuemonitor](/sql/relational-databases/system-stored-procedures/sp-replqueuemonitor-transact-sql) at each Subscriber.</span></span>  
  
3.  <span data-ttu-id="e9ddb-116">En la base de datos de publicación del publicador, ejecute [sp_posttracertoken](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9ddb-116">At the Publisher on the publication database, execute [sp_posttracertoken](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span></span>  
  
4.  <span data-ttu-id="e9ddb-117">En la base de datos de publicación del publicador, ejecute [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9ddb-117">At the Publisher on the publication database, execute [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span></span>  
  
5.  <span data-ttu-id="e9ddb-118">Asegúrese de que cada suscriptor ha recibido el token de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-118">Ensure that each Subscriber has received the tracer token.</span></span>  
  
### <a name="to-quiesce-a-peer-to-peer-transactional-replication-topology"></a><span data-ttu-id="e9ddb-119">Para detener una topología de replicación transaccional punto a punto</span><span class="sxs-lookup"><span data-stu-id="e9ddb-119">To quiesce a peer-to-peer transactional replication topology</span></span>  
  
1.  <span data-ttu-id="e9ddb-120">Detenga la actividad en todas las tablas de todos los nodos.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-120">Stop activity on all published tables at all nodes.</span></span>  
  
2.  <span data-ttu-id="e9ddb-121">Ejecute [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) en cada base de datos de publicación de la topología.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-121">Execute [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) on each publication database in the topology.</span></span>  
  
3.  <span data-ttu-id="e9ddb-122">Si el Agente de registro del LOG o el Agente de distribución no se está ejecutando de forma continua, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-122">If the Log Reader Agent or Distribution Agent is not running in continuous mode, run the agent.</span></span> <span data-ttu-id="e9ddb-123">El Agente de registro del LOG se debe iniciar antes del Agente de distribución.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-123">The Log Reader Agent must be started before the Distribution Agent.</span></span> <span data-ttu-id="e9ddb-124">Para obtener más información sobre la ejecución de agentes, vea [Conceptos de los ejecutables del Agente de replicación](../concepts/replication-agent-executables-concepts.md) o [Iniciar y detener un agente de replicación &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e9ddb-124">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
4.  <span data-ttu-id="e9ddb-125">Ejecute [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) en cada base de datos de publicación de la topología.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-125">Execute [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) on each publication database in the topology.</span></span> <span data-ttu-id="e9ddb-126">Asegúrese de que el conjunto de resultados contiene las respuestas de cada uno de los otros nodos.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-126">Ensure that the result set contains responses from each of the other nodes.</span></span>  
  
### <a name="to-ensure-a-peer-to-peer-node-has-received-all-prior-changes"></a><span data-ttu-id="e9ddb-127">Para asegurarse de que un nodo punto a punto ha recibido todos los cambios anteriores</span><span class="sxs-lookup"><span data-stu-id="e9ddb-127">To ensure a peer-to-peer node has received all prior changes</span></span>  
  
1.  <span data-ttu-id="e9ddb-128">Ejecute [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) en la base de datos de publicación del nodo que está comprobando.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-128">Execute [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) on the publication database at the node you are checking.</span></span>  
  
2.  <span data-ttu-id="e9ddb-129">Si el Agente de registro del LOG o el Agente de distribución no se está ejecutando de forma continua, ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-129">If the Log Reader Agent or Distribution Agent is not running in continuous mode, run the agent.</span></span> <span data-ttu-id="e9ddb-130">El Agente de registro del LOG se debe iniciar antes del Agente de distribución.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-130">The Log Reader Agent must be started before the Distribution Agent.</span></span> <span data-ttu-id="e9ddb-131">Para obtener más información sobre la ejecución de agentes, vea [Conceptos de los ejecutables del Agente de replicación](../concepts/replication-agent-executables-concepts.md) o [Iniciar y detener un agente de replicación &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e9ddb-131">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
3.  <span data-ttu-id="e9ddb-132">Ejecute [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) en la base de datos de publicación del nodo que está comprobando.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-132">Execute [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) on the publication database at the node you are checking.</span></span> <span data-ttu-id="e9ddb-133">Asegúrese de que el conjunto de resultados contiene las respuestas de cada uno de los otros nodos.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-133">Ensure that the result set contains responses from each of the other nodes.</span></span>  
  
### <a name="to-quiesce-a-merge-replication-topology"></a><span data-ttu-id="e9ddb-134">Para detener una topología de replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="e9ddb-134">To quiesce a merge replication topology</span></span>  
  
1.  <span data-ttu-id="e9ddb-135">Detenga la actividad en todas las tablas en el publicador y en todos los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-135">Stop activity on all published tables at the Publisher and at all Subscribers.</span></span>  
  
2.  <span data-ttu-id="e9ddb-136">Ejecute el Agente de mezcla para cada suscripción dos veces: sincronice todas las suscripciones una vez y, a continuación, sincronice cada suscripción una segunda vez.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-136">Run the Merge Agent for each subscription two times: synchronize all subscriptions once and then synchronize each subscription a second time.</span></span> <span data-ttu-id="e9ddb-137">Con esto se asegura de que todos los cambios se han replicado en todos los nodos.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-137">This ensures that all changes are replicated to all nodes.</span></span> <span data-ttu-id="e9ddb-138">Para obtener más información sobre la ejecución de agentes, vea [Conceptos de los ejecutables del Agente de replicación](../concepts/replication-agent-executables-concepts.md) o [Iniciar y detener un agente de replicación &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e9ddb-138">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e9ddb-139">Si se producen conflictos durante la sincronización, es posible que los cambios requeridos por la resolución de conflictos no se propaguen a todos los nodos después de ejecutar el Agente de mezcla dos veces.</span><span class="sxs-lookup"><span data-stu-id="e9ddb-139">If conflicts occur during synchronization, it is possible that changes required by conflict resolution will not be propagated to all nodes after running the Merge Agent two times.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ddb-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9ddb-140">See Also</span></span>  
 <span data-ttu-id="e9ddb-141">[Administrar una topología punto a punto &#40;programación de la replicación con Transact-SQL&#41;](administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span><span class="sxs-lookup"><span data-stu-id="e9ddb-141">[Administer a Peer-to-Peer Topology &#40;Replication Transact-SQL Programming&#41;](administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span></span>  
 [<span data-ttu-id="e9ddb-142">Medir la latencia y validar las conexiones de la replicación transaccional</span><span class="sxs-lookup"><span data-stu-id="e9ddb-142">Measure Latency and Validate Connections for Transactional Replication</span></span>](../monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
  
