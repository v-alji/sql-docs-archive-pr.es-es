---
title: Supervisión de agentes de replicación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], agents
- Log Reader Agent, monitoring
- Replication Monitor, agents
- Merge Agent, monitoring
- Queue Reader Agent, monitoring
- Snapshot Agent, monitoring
- agents [SQL Server replication], monitoring
- Distribution Agent, monitoring
ms.assetid: d06ed24f-82d7-4b9e-9e40-cc9780476a71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: baa22ef9e9f7c4621f76838e82c309d17f1e12a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670932"
---
# <a name="monitor-replication-agents"></a><span data-ttu-id="92f36-102">Supervisar agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="92f36-102">Monitor Replication Agents</span></span>
  <span data-ttu-id="92f36-103">El Monitor de replicación de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proporciona una vista sistémica de la actividad de replicación, aunque también facilita la búsqueda de información en un agente concreto.</span><span class="sxs-lookup"><span data-stu-id="92f36-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor provides a systemic view of replication activity, but also makes it straightforward to find information on a specific agent.</span></span> <span data-ttu-id="92f36-104">En la siguiente lista se incluye cada agente, las pestañas del Monitor de replicación en las que se puede encontrar y un vínculo a un tema en el que se explica el modo de obtener acceso a dichas pestañas:</span><span class="sxs-lookup"><span data-stu-id="92f36-104">The following list includes each agent, the tabs in the Replication Monitor on which it can be found, and a link to a topic that explains how to access these tabs:</span></span>  
  
-   <span data-ttu-id="92f36-105">Los siguientes agentes están asociados con publicaciones en el Monitor de replicación:</span><span class="sxs-lookup"><span data-stu-id="92f36-105">The following agents are associated with publications in Replication Monitor:</span></span>  
  
    -   <span data-ttu-id="92f36-106">Agente de instantáneas</span><span class="sxs-lookup"><span data-stu-id="92f36-106">Snapshot Agent</span></span>  
  
    -   <span data-ttu-id="92f36-107">Agente de registro del LOG</span><span class="sxs-lookup"><span data-stu-id="92f36-107">Log Reader Agent</span></span>  
  
    -   <span data-ttu-id="92f36-108">Agente de lectura de cola</span><span class="sxs-lookup"><span data-stu-id="92f36-108">Queue Reader Agent</span></span>  
  
     <span data-ttu-id="92f36-109">Acceda a la información y a las tareas asociadas con estos agentes a través de las pestañas siguientes: **Agentes** (disponible para todos los publicadores y publicaciones) y **Advertencias** (disponible para todas las publicaciones).</span><span class="sxs-lookup"><span data-stu-id="92f36-109">Access information and tasks associated with these agents through the following tabs: **Agents** (available for each Publisher and publication) and **Warnings** (available for each publication).</span></span> <span data-ttu-id="92f36-110">Para más información, vea [Visualización de información y realización de tareas mediante el Monitor de replicación](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="92f36-110">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="92f36-111">Los siguientes agentes están asociados con suscripciones en el Monitor de replicación:</span><span class="sxs-lookup"><span data-stu-id="92f36-111">The following agents are associated with subscriptions in Replication Monitor:</span></span>  
  
    -   <span data-ttu-id="92f36-112">Agente de distribución</span><span class="sxs-lookup"><span data-stu-id="92f36-112">Distribution Agent</span></span>  
  
    -   <span data-ttu-id="92f36-113">Agente de mezcla</span><span class="sxs-lookup"><span data-stu-id="92f36-113">Merge Agent</span></span>  
  
     <span data-ttu-id="92f36-114">Acceda a la información y a las tareas asociadas con estos agentes a través de las pestañas siguientes: **Lista de supervisión de suscripciones** (disponible para todos los publicadores) o la pestaña **Todas las suscripciones** (disponible para todas las publicaciones).</span><span class="sxs-lookup"><span data-stu-id="92f36-114">Access information and tasks associated with these agents through the following tabs: **Subscription Watch List** (available for each Publisher) or the **All Subscriptions** tab (available for each publication).</span></span> <span data-ttu-id="92f36-115">Para más información, vea [Visualización de información y realización de tareas mediante el Monitor de replicación](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="92f36-115">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
## <a name="using-sql-server-management-studio-to-monitor-replication-agents"></a><span data-ttu-id="92f36-116">Usar SQL Server Management Studio para supervisar agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="92f36-116">Using SQL Server Management Studio to Monitor Replication Agents</span></span>  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="92f36-117">[!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] proporciona los siguientes cuadros de diálogo para supervisar agentes de replicación:</span><span class="sxs-lookup"><span data-stu-id="92f36-117">[!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] provides the following dialog boxes for monitoring replication agents:</span></span>  
  
-   <span data-ttu-id="92f36-118">**Ver estado del Agente de instantáneas** (para todas las publicaciones)</span><span class="sxs-lookup"><span data-stu-id="92f36-118">**View Snapshot Agent Status** (for all publications)</span></span>  
  
-   <span data-ttu-id="92f36-119">**Ver estado del Agente de registro del LOG** (para todas las publicaciones transaccionales)</span><span class="sxs-lookup"><span data-stu-id="92f36-119">**View Log Reader Agent Status** (for all transactional publications)</span></span>  
  
-   <span data-ttu-id="92f36-120">**Ver estado de sincronización** (para todas las suscripciones; este cuadro de diálogo permite el acceso al Agente de distribución y al Agente de mezcla)</span><span class="sxs-lookup"><span data-stu-id="92f36-120">**View Synchronization Status** (for all subscriptions; this dialog box allows access to the Distribution Agent and the Merge Agent)</span></span>  
  
 <span data-ttu-id="92f36-121">El Monitor de replicación proporciona información adicional sobre cada agente y ofrece la posibilidad de supervisar al Agente de lectura de cola, si se utiliza.</span><span class="sxs-lookup"><span data-stu-id="92f36-121">Replication Monitor provides additional information about each agent and provides monitoring for the Queue Reader Agent, if it is used.</span></span> <span data-ttu-id="92f36-122">Para más información, vea [Visualización de información y realización de tareas mediante el Monitor de replicación](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="92f36-122">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
#### <a name="to-monitor-the-snapshot-agent-and-log-reader-agent"></a><span data-ttu-id="92f36-123">Para supervisar el Agente de instantáneas y el Agente de registro del LOG</span><span class="sxs-lookup"><span data-stu-id="92f36-123">To monitor the Snapshot Agent and Log Reader Agent</span></span>  
  
1.  <span data-ttu-id="92f36-124">Conéctese al publicador en [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]y luego expanda el nodo del servidor.</span><span class="sxs-lookup"><span data-stu-id="92f36-124">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="92f36-125">Expanda la carpeta **Replicación** y, a continuación, expanda la carpeta **Publicaciones locales** .</span><span class="sxs-lookup"><span data-stu-id="92f36-125">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="92f36-126">Haga clic con el botón secundario en una publicación y, a continuación, en **Ver estado del Agente de registro del LOG** o en **Ver estado del Agente de instantáneas**.</span><span class="sxs-lookup"><span data-stu-id="92f36-126">Right-click a publication, and then click **View Log Reader Agent Status** or **View Snapshot Agent Status**.</span></span>  
  
4.  <span data-ttu-id="92f36-127">En el cuadro de diálogo **Ver estado del Agente de registro del LOG** o **Ver estado del Agente de instantáneas** :</span><span class="sxs-lookup"><span data-stu-id="92f36-127">In the **View Log Reader Agent Status** or **View Snapshot Agent Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="92f36-128">Vea el estado del agente.</span><span class="sxs-lookup"><span data-stu-id="92f36-128">View agent status.</span></span>  
  
    -   <span data-ttu-id="92f36-129">Inicie o detenga el agente si fuese necesario.</span><span class="sxs-lookup"><span data-stu-id="92f36-129">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="92f36-130">Haga clic en **Supervisar** para iniciar el **Monitor de replicación**.</span><span class="sxs-lookup"><span data-stu-id="92f36-130">Click **Monitor** to launch **Replication Monitor**.</span></span>  
  
5.  <span data-ttu-id="92f36-131">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="92f36-131">Click **Close**.</span></span>  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-publisher"></a><span data-ttu-id="92f36-132">Para supervisar el Agente de distribución y el Agente de mezcla (en el publicador)</span><span class="sxs-lookup"><span data-stu-id="92f36-132">To monitor the Distribution Agent and Merge Agent (from the Publisher)</span></span>  
  
1.  <span data-ttu-id="92f36-133">Conéctese al publicador en [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]y luego expanda el nodo del servidor.</span><span class="sxs-lookup"><span data-stu-id="92f36-133">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="92f36-134">Expanda la carpeta **Replicación** y, a continuación, expanda la carpeta **Publicaciones locales** .</span><span class="sxs-lookup"><span data-stu-id="92f36-134">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="92f36-135">Expanda la publicación de la suscripción que desea supervisar.</span><span class="sxs-lookup"><span data-stu-id="92f36-135">Expand the publication for the subscription you want to monitor.</span></span>  
  
4.  <span data-ttu-id="92f36-136">Haga clic con el botón secundario en la suscripción y, a continuación, haga clic en **Ver estado de sincronización**.</span><span class="sxs-lookup"><span data-stu-id="92f36-136">Right-click the subscription, and then click **View Synchronization Status**.</span></span>  
  
5.  <span data-ttu-id="92f36-137">En el cuadro de diálogo **Ver estado de sincronización** :</span><span class="sxs-lookup"><span data-stu-id="92f36-137">In the **View Synchronization Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="92f36-138">Vea el estado del agente.</span><span class="sxs-lookup"><span data-stu-id="92f36-138">View agent status.</span></span>  
  
    -   <span data-ttu-id="92f36-139">Inicie o detenga el agente si fuese necesario.</span><span class="sxs-lookup"><span data-stu-id="92f36-139">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="92f36-140">Para las suscripciones de inserción, haga clic en **Supervisar** para iniciar el **Monitor de replicación**.</span><span class="sxs-lookup"><span data-stu-id="92f36-140">For push subscriptions, click **Monitor** to launch **Replication Monitor**.</span></span>  
  
    -   <span data-ttu-id="92f36-141">Para las suscripciones de extracción, haga clic en **Ver historial de trabajos** para iniciar el **Visor del archivo de registros**, que muestra información sobre el registro del agente.</span><span class="sxs-lookup"><span data-stu-id="92f36-141">For pull subscriptions, click **View Job History** to launch the **Log File Viewer**, which displays output from the agent log.</span></span>  
  
6.  <span data-ttu-id="92f36-142">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="92f36-142">Click **Close**.</span></span>  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-subscriber"></a><span data-ttu-id="92f36-143">Para supervisar el Agente de distribución y el Agente de mezcla (en el suscriptor)</span><span class="sxs-lookup"><span data-stu-id="92f36-143">To monitor the Distribution Agent and Merge Agent (from the Subscriber)</span></span>  
  
1.  <span data-ttu-id="92f36-144">Conéctese al suscriptor en [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]y expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="92f36-144">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="92f36-145">Expanda la carpeta **Replicación** y, a continuación, la carpeta **Suscripciones locales**.</span><span class="sxs-lookup"><span data-stu-id="92f36-145">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="92f36-146">Haga clic con el botón secundario en la suscripción que desee supervisar y, a continuación, haga clic en **Ver estado de sincronización**.</span><span class="sxs-lookup"><span data-stu-id="92f36-146">Right-click the subscription you want to monitor, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="92f36-147">En el cuadro de diálogo **Ver estado de sincronización** :</span><span class="sxs-lookup"><span data-stu-id="92f36-147">In the **View Synchronization Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="92f36-148">Vea el estado del agente.</span><span class="sxs-lookup"><span data-stu-id="92f36-148">View agent status.</span></span>  
  
    -   <span data-ttu-id="92f36-149">Inicie o detenga el agente si fuese necesario.</span><span class="sxs-lookup"><span data-stu-id="92f36-149">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="92f36-150">Haga clic en **Ver historial de trabajos** para iniciar el **Visor del archivo de registros**, que muestra información sobre el registro del agente.</span><span class="sxs-lookup"><span data-stu-id="92f36-150">Click **View Job History** to launch the **Log File Viewer**, which displays output from the agent log.</span></span>  
  
5.  <span data-ttu-id="92f36-151">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="92f36-151">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92f36-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92f36-152">See Also</span></span>  
 <span data-ttu-id="92f36-153">[Monitoring Replication](../monitoring-replication.md)  (Supervisar la replicación)</span><span class="sxs-lookup"><span data-stu-id="92f36-153">[Monitoring Replication](../monitoring-replication.md) </span></span>  
 [<span data-ttu-id="92f36-154">Información general sobre los agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="92f36-154">Replication Agents Overview</span></span>](../agents/replication-agents-overview.md)  
  
  
