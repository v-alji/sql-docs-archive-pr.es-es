---
title: MSSQL_ENG014161 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014161 error
ms.assetid: 4b983e76-bb77-43c5-b44b-19919d3da619
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8cf85181e444385e1a3908761ba71414b68cf3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661931"
---
# <a name="mssql_eng014161"></a><span data-ttu-id="63f19-102">MSSQL_ENG014161</span><span class="sxs-lookup"><span data-stu-id="63f19-102">MSSQL_ENG014161</span></span>
    
## <a name="message-details"></a><span data-ttu-id="63f19-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="63f19-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="63f19-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="63f19-104">Product Name</span></span>|<span data-ttu-id="63f19-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="63f19-105">SQL Server</span></span>|  
|<span data-ttu-id="63f19-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="63f19-106">Event ID</span></span>|<span data-ttu-id="63f19-107">14161</span><span class="sxs-lookup"><span data-stu-id="63f19-107">14161</span></span>|  
|<span data-ttu-id="63f19-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="63f19-108">Event Source</span></span>|<span data-ttu-id="63f19-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="63f19-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="63f19-110">Componente</span><span class="sxs-lookup"><span data-stu-id="63f19-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="63f19-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="63f19-111">Symbolic Name</span></span>||  
|<span data-ttu-id="63f19-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="63f19-112">Message Text</span></span>|<span data-ttu-id="63f19-113">Se ha establecido el umbral [%s:%s] para la publicación [%s].</span><span class="sxs-lookup"><span data-stu-id="63f19-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="63f19-114">Asegúrese de que los agentes de registro del LOG y de distribución se están ejecutando y cumplen con el requisito de latencia.</span><span class="sxs-lookup"><span data-stu-id="63f19-114">Make sure that the logreader and distribution agents are running and can match the latency requirement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="63f19-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="63f19-115">Explanation</span></span>  
 <span data-ttu-id="63f19-116">La replicación le permite habilitar advertencias para varias condiciones.</span><span class="sxs-lookup"><span data-stu-id="63f19-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="63f19-117">Incluye la superación de una latencia específica en suscripciones transaccionales.</span><span class="sxs-lookup"><span data-stu-id="63f19-117">This includes exceeding a specified latency for transactional subscriptions.</span></span> <span data-ttu-id="63f19-118">Latencia es el tiempo que transcurre entre la confirmación de un cambio de datos en el publicador y la confirmación del cambio correspondiente en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="63f19-118">Latency is the period of time that elapses between a data change being committed at the Publisher and the corresponding change being committed at the Subscriber.</span></span>  
  
 <span data-ttu-id="63f19-119">Al habilitar una advertencia mediante el Monitor de replicación o [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), especifica un umbral que determina cuándo se desencadena una advertencia.</span><span class="sxs-lookup"><span data-stu-id="63f19-119">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="63f19-120">Cuando se alcanza o se supera un umbral, aparece una advertencia en el Monitor de replicación y se escribe un evento en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="63f19-120">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="63f19-121">Alcanzar un umbral también puede desencadenar una alerta del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="63f19-121">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="63f19-122">Para obtener más información, vea [Establecer umbrales y advertencias en el Monitor de replicación](monitor/set-thresholds-and-warnings-in-replication-monitor.md) y [Cómo supervisar la replicación mediante programación (programación con RMO)](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="63f19-122">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="63f19-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="63f19-123">User Action</span></span>  
 <span data-ttu-id="63f19-124">Si una suscripción supera un umbral de latencia, debe determinar si hay algún problema de rendimiento en el sistema o si debe ajustarse el umbral.</span><span class="sxs-lookup"><span data-stu-id="63f19-124">If a subscription exceeds a latency threshold, you must determine whether there is a performance issue with the system or whether the threshold should be adjusted.</span></span> <span data-ttu-id="63f19-125">Una vez configurada la replicación, desarrolle una línea base de rendimiento que le permitirá determinar el comportamiento de la replicación con la carga de trabajo habitual de las aplicaciones y la topología.</span><span class="sxs-lookup"><span data-stu-id="63f19-125">After you configure replication, develop a performance baseline that will let you determine how replication behaves with a workload that is typical for your applications and topology.</span></span> <span data-ttu-id="63f19-126">Incluya la latencia en esta línea base para poder establecer un valor adecuado para el umbral.</span><span class="sxs-lookup"><span data-stu-id="63f19-126">Include latency in this baseline so that you can set an appropriate value for the threshold.</span></span>  
  
 <span data-ttu-id="63f19-127">Si el valor del umbral es adecuado, pero está siendo superado, debe determinar dónde se encuentra el cuello de botella en el sistema.</span><span class="sxs-lookup"><span data-stu-id="63f19-127">If the threshold value is appropriate, but it is being exceeded, you must determine where the performance bottleneck is in the system.</span></span> <span data-ttu-id="63f19-128">Para obtener más información acerca de cómo supervisar y solucionar problemas relacionados con el rendimiento de replicación, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="63f19-128">For more information about how to monitor and troubleshoot replication performance, see the following topics:</span></span>  
  
-   [<span data-ttu-id="63f19-129">Medir la latencia y validar las conexiones de la replicación transaccional</span><span class="sxs-lookup"><span data-stu-id="63f19-129">Measure Latency and Validate Connections for Transactional Replication</span></span>](monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
-   [<span data-ttu-id="63f19-130">Supervisar el rendimiento con el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="63f19-130">Monitor Performance with Replication Monitor</span></span>](monitor/monitor-performance-with-replication-monitor.md)  
  
## <a name="see-also"></a><span data-ttu-id="63f19-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63f19-131">See Also</span></span>  
 [<span data-ttu-id="63f19-132">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="63f19-132">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
