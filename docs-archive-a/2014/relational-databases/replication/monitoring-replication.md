---
title: Supervisión de la replicación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], about monitoring replication
- transactional replication, monitoring
- monitoring [SQL Server replication]
- merge replication monitoring [SQL Server replication]
- snapshot replication [SQL Server], monitoring
- replication [SQL Server], monitoring
- administering replication, monitoring
ms.assetid: f182f43a-6af8-45bc-a708-08d5f7a6984a
author: rothja
ms.author: jroth
ms.openlocfilehash: df2760e4ce04c95f38ceb9dfe9fa9f79c4c467f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746947"
---
# <a name="monitoring-replication"></a><span data-ttu-id="9d669-102">Supervisar (replicación)</span><span class="sxs-lookup"><span data-stu-id="9d669-102">Monitoring (Replication)</span></span>
  <span data-ttu-id="9d669-103">Supervisar una topología de replicación es un aspecto importante en la implementación de la replicación.</span><span class="sxs-lookup"><span data-stu-id="9d669-103">Monitoring a replication topology is an important aspect of deploying replication.</span></span> <span data-ttu-id="9d669-104">Debido a que la actividad de replicación se distribuye, es fundamental realizar un seguimiento de la actividad y el estado de todos los equipos que participan en la replicación.</span><span class="sxs-lookup"><span data-stu-id="9d669-104">Because replication activity is distributed, it is essential to track activity and status across all computers involved in replication.</span></span> <span data-ttu-id="9d669-105">Para supervisar la replicación se pueden utilizar las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="9d669-105">The following tools can be used to monitor replication:</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msCoName-md.md)]<span data-ttu-id="9d669-106">[!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)]Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="9d669-106">[!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)] Replication Monitor</span></span>  
  
     <span data-ttu-id="9d669-107">El Monitor de replicación es la herramienta más importante para supervisar la replicación, ya que presenta una vista de la actividad de la replicación centrada en el publicador.</span><span class="sxs-lookup"><span data-stu-id="9d669-107">Replication Monitor is the most important tool for monitoring replication, presenting a Publisher-focused view of all replication activity.</span></span> <span data-ttu-id="9d669-108">Para obtener más información, vea [supervisar el rendimiento con el monitor de replicación](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="9d669-108">For more information, see [Monitor performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msCoName-md.md)] <span data-ttu-id="9d669-109">[!INCLUDE[ssManStudioFull](../../includes/ssManStudioFull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d669-109">[!INCLUDE[ssManStudioFull](../../includes/ssManStudioFull-md.md)]</span></span>  
  
     [!INCLUDE[ssManStudio](../../includes/ssManStudio-md.md)] <span data-ttu-id="9d669-110">proporciona acceso al Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="9d669-110">provides access to Replication Monitor.</span></span> <span data-ttu-id="9d669-111">También permite ver el estado actual y el último mensaje registrado por los siguientes agentes, además de permitir iniciar y detener cada agente: Agente de registro del LOG, Agente de instantáneas, Agente de mezcla y Agente de distribución.</span><span class="sxs-lookup"><span data-stu-id="9d669-111">It also allows you to view the current status and last message logged by the following agents and allows you start and stop each agent: Log Reader Agent, Snapshot Agent, Merge Agent, and Distribution Agent.</span></span> <span data-ttu-id="9d669-112">Para más información, consulte [Monitor Replication Agents](monitor/monitor-replication-agents.md).</span><span class="sxs-lookup"><span data-stu-id="9d669-112">For more information, see [Monitor Replication Agents](monitor/monitor-replication-agents.md).</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="9d669-113">y Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="9d669-113">and Replication Management Objects (RMO)</span></span>  
  
     <span data-ttu-id="9d669-114">Ambas interfaces le permiten supervisar todos los tipos de replicación desde el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="9d669-114">Both interfaces allow you to monitor all types of replication from the Distributor.</span></span> <span data-ttu-id="9d669-115">La replicación de mezcla también ofrece la posibilidad de supervisar la replicación desde el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="9d669-115">Merge replication also provides the ability to monitor replication from the Subscriber.</span></span>  
  
-   <span data-ttu-id="9d669-116">Alertas para eventos de agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="9d669-116">Alerts for replication agent events</span></span>  
  
     <span data-ttu-id="9d669-117">La replicación proporciona una serie de alertas predefinidas para los eventos de los agentes de replicación y se pueden crear alertas adicionales si es necesario.</span><span class="sxs-lookup"><span data-stu-id="9d669-117">Replication provides a number of predefined alerts for replication agent events, and you can create additional alerts if necessary.</span></span> <span data-ttu-id="9d669-118">Las alertas se pueden utilizar para desencadenar una respuesta automática a un evento y para notificar a un administrador.</span><span class="sxs-lookup"><span data-stu-id="9d669-118">Alerts can be used to trigger an automated response to an event and/or notify an administrator.</span></span> <span data-ttu-id="9d669-119">Para obtener más información, vea [Usar alertas para eventos del Agente de replicación](agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="9d669-119">For more information, see [Use Alerts for Replication Agent Events](agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
-   <span data-ttu-id="9d669-120">Monitor de sistema</span><span class="sxs-lookup"><span data-stu-id="9d669-120">System Monitor</span></span>  
  
     <span data-ttu-id="9d669-121">El Monitor de sistema puede resultar útil para supervisar el rendimiento, ya que proporciona una serie de contadores para la replicación.</span><span class="sxs-lookup"><span data-stu-id="9d669-121">System Monitor can be useful for monitoring performance, providing a number of counters for replication.</span></span> <span data-ttu-id="9d669-122">Para más información, consulte [Monitoring Replication with System Monitor](monitor/monitoring-replication-with-system-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="9d669-122">For more information, see [Monitoring Replication with System Monitor](monitor/monitoring-replication-with-system-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d669-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d669-123">See Also</span></span>  
 <span data-ttu-id="9d669-124">[Preguntas más frecuentes para administradores de replicación](administration/frequently-asked-questions-for-replication-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="9d669-124">[Replication Administration FAQ](administration/frequently-asked-questions-for-replication-administrators.md) </span></span>  
 [<span data-ttu-id="9d669-125">Best Practices for Replication Administration</span><span class="sxs-lookup"><span data-stu-id="9d669-125">Best Practices for Replication Administration</span></span>](administration/best-practices-for-replication-administration.md)   

  
  
