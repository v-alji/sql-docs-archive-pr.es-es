---
title: MSSQL_ENG014160 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014160 error
ms.assetid: d0f3855e-d095-4a81-a5bd-9d7ad51f2c77
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3351567a31a0a0384ab8957073ab0457ef0ea7c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662821"
---
# <a name="mssql_eng014160"></a><span data-ttu-id="89e1e-102">MSSQL_ENG014160</span><span class="sxs-lookup"><span data-stu-id="89e1e-102">MSSQL_ENG014160</span></span>
    
## <a name="message-details"></a><span data-ttu-id="89e1e-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="89e1e-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="89e1e-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="89e1e-104">Product Name</span></span>|<span data-ttu-id="89e1e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="89e1e-105">SQL Server</span></span>|  
|<span data-ttu-id="89e1e-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="89e1e-106">Event ID</span></span>|<span data-ttu-id="89e1e-107">14160</span><span class="sxs-lookup"><span data-stu-id="89e1e-107">14160</span></span>|  
|<span data-ttu-id="89e1e-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="89e1e-108">Event Source</span></span>|<span data-ttu-id="89e1e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="89e1e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="89e1e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="89e1e-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="89e1e-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="89e1e-111">Symbolic Name</span></span>||  
|<span data-ttu-id="89e1e-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="89e1e-112">Message Text</span></span>|<span data-ttu-id="89e1e-113">Se ha establecido el umbral [%s:%s] para la publicación [%s].</span><span class="sxs-lookup"><span data-stu-id="89e1e-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="89e1e-114">Han expirado una o más suscripciones a esta publicación.</span><span class="sxs-lookup"><span data-stu-id="89e1e-114">One or more subscriptions to this publication have expired.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="89e1e-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="89e1e-115">Explanation</span></span>  
 <span data-ttu-id="89e1e-116">La replicación le permite habilitar advertencias para varias condiciones.</span><span class="sxs-lookup"><span data-stu-id="89e1e-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="89e1e-117">Esto incluye la expiración inminente de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="89e1e-117">This includes imminent subscription expiration.</span></span> <span data-ttu-id="89e1e-118">Las suscripciones pueden expirar si no se sincronizan en un *período de retención*especificado.</span><span class="sxs-lookup"><span data-stu-id="89e1e-118">Subscriptions can expire if they are not synchronized within a specified *retention period*.</span></span> <span data-ttu-id="89e1e-119">Para más información, consulte [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="89e1e-119">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
 <span data-ttu-id="89e1e-120">Al habilitar una advertencia mediante el Monitor de replicación o [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), especifica un umbral que determina cuándo se desencadena una advertencia.</span><span class="sxs-lookup"><span data-stu-id="89e1e-120">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="89e1e-121">Cuando se alcanza o se supera un umbral, aparece una advertencia en el Monitor de replicación y se escribe un evento en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="89e1e-121">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="89e1e-122">Alcanzar un umbral también puede desencadenar una alerta del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="89e1e-122">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="89e1e-123">Para obtener más información, vea [Establecer umbrales y advertencias en el Monitor de replicación](monitor/set-thresholds-and-warnings-in-replication-monitor.md) y [Cómo supervisar la replicación mediante programación (programación con RMO)](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="89e1e-123">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="89e1e-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="89e1e-124">User Action</span></span>  
 <span data-ttu-id="89e1e-125">La resolución de este problema depende del motivo por el que se produjo la advertencia:</span><span class="sxs-lookup"><span data-stu-id="89e1e-125">The resolution for this issue depends on the reason the warning was raised:</span></span>  
  
-   <span data-ttu-id="89e1e-126">Si se ha sobrepasado el umbral, pero la suscripción no ha expirado todavía, sincronice la suscripción.</span><span class="sxs-lookup"><span data-stu-id="89e1e-126">If the threshold has been exceeded, but the subscription has not yet expired, synchronize the subscription.</span></span> <span data-ttu-id="89e1e-127">Para obtener más información, vea [Sincronizar datos](synchronize-data.md).</span><span class="sxs-lookup"><span data-stu-id="89e1e-127">For more information, see [Synchronize Data](synchronize-data.md).</span></span>  
  
-   <span data-ttu-id="89e1e-128">Si el agente se ha estado ejecutando, pero no ha estado replicando los cambios correctamente, puede provocar que la suscripción expire.</span><span class="sxs-lookup"><span data-stu-id="89e1e-128">If the agent has been running, but has not been replicating changes properly, this can cause the subscription to expire.</span></span> <span data-ttu-id="89e1e-129">En la replicación transaccional, asegúrese de que se están ejecutando el Agente de distribución o el Agente de registro del LOG.</span><span class="sxs-lookup"><span data-stu-id="89e1e-129">For transactional replication, make sure that the Distribution Agent and Log Reader Agent are running.</span></span> <span data-ttu-id="89e1e-130">En la replicación de mezcla, asegúrese de que se está ejecutando el Agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="89e1e-130">For merge replication, make sure the Merge Agent is running.</span></span> <span data-ttu-id="89e1e-131">Para obtener información sobre cómo ejecutar estos agentes, vea [Iniciar y detener un agente de replicación &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) y [Conceptos de los ejecutables del Agente de replicación](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="89e1e-131">For information about how to start these agents, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="89e1e-132">Si la suscripción ha expirado, debe ser reinicializada o bien quitada y creada nuevamente, dependiendo del tipo de suscripción y durante cuanto tiempo ha expirado.</span><span class="sxs-lookup"><span data-stu-id="89e1e-132">If the subscription has expired, it must either be reinitialized or dropped and re-created, depending on the type of subscription and how long it has been expired.</span></span> <span data-ttu-id="89e1e-133">Para más información, consulte [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="89e1e-133">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e1e-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89e1e-134">See Also</span></span>  
 [<span data-ttu-id="89e1e-135">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="89e1e-135">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
