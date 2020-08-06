---
title: Iniciar y detener un agente de replicación (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], stopping
- agents [SQL Server replication], starting
ms.assetid: 97977c4a-8c7c-4a22-9480-69aa812bd1e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b40e329e0f04e8a54a2d5a40c30aff418da2cd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663414"
---
# <a name="start-and-stop-a-replication-agent-sql-server-management-studio"></a><span data-ttu-id="507bd-102">Iniciar y detener un agente de replicación (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="507bd-102">Start and Stop a Replication Agent (SQL Server Management Studio)</span></span>
  <span data-ttu-id="507bd-103">Puede iniciar y detener agentes desde las carpetas **Trabajos** y **Replicación** de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] y desde el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="507bd-103">Start and stop agents from the **Jobs** folder and the **Replication** folder in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from Replication Monitor.</span></span> <span data-ttu-id="507bd-104">Inicie y detenga los siguientes agentes y trabajos:</span><span class="sxs-lookup"><span data-stu-id="507bd-104">Start and stop the following agents and jobs:</span></span>  
  
-   <span data-ttu-id="507bd-105">El Agente de instantáneas, utilizado por todas las publicaciones.</span><span class="sxs-lookup"><span data-stu-id="507bd-105">The Snapshot Agent, which is used by all publications.</span></span>  
  
-   <span data-ttu-id="507bd-106">El Agente de registro del LOG, utilizado por todas las publicaciones transaccionales.</span><span class="sxs-lookup"><span data-stu-id="507bd-106">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
-   <span data-ttu-id="507bd-107">El Agente de lectura de cola, utilizado por las publicaciones transaccionales con suscripciones de actualización en cola habilitadas.</span><span class="sxs-lookup"><span data-stu-id="507bd-107">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="507bd-108">El Agente de distribución, que sincroniza las suscripciones con las publicaciones transaccionales y de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="507bd-108">The Distribution Agent, which synchronizes subscriptions to transactional and snapshot publications.</span></span>  
  
-   <span data-ttu-id="507bd-109">El Agente de mezcla, que sincroniza las suscripciones con las publicaciones de combinación.</span><span class="sxs-lookup"><span data-stu-id="507bd-109">The Merge Agent, which synchronizes subscriptions to merge publications.</span></span>  
  
-   <span data-ttu-id="507bd-110">Trabajos de mantenimiento de la replicación.</span><span class="sxs-lookup"><span data-stu-id="507bd-110">Replication maintenance jobs.</span></span>  
  
 <span data-ttu-id="507bd-111">Para más información sobre cómo iniciar el Agente de mezcla y el Agente de distribución, vea [Sincronizar una suscripción de inserción](../synchronize-a-push-subscription.md) y [Sincronizar una suscripción de extracción](../synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="507bd-111">For more information about starting the Merge Agent and the Distribution Agent, see [Synchronize a Push Subscription](../synchronize-a-push-subscription.md) and [Synchronize a Pull Subscription](../synchronize-a-pull-subscription.md).</span></span> <span data-ttu-id="507bd-112">Para más información acerca de los trabajos de mantenimiento, vea [Ejecutar trabajos de mantenimiento de replicación &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="507bd-112">For more information about maintenance jobs, see [Run Replication Maintenance Jobs &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md).</span></span>  
  
 <span data-ttu-id="507bd-113">Para información sobre cómo iniciar el Monitor de replicación, vea [Iniciar el Monitor de replicación](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="507bd-113">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span>  
  
### <a name="to-start-and-stop-a-snapshot-agent-or-log-reader-agent-from-management-studio"></a><span data-ttu-id="507bd-114">Para iniciar y detener un agente de instantáneas o un agente de registro del LOG desde Management Studio</span><span class="sxs-lookup"><span data-stu-id="507bd-114">To start and stop a Snapshot Agent or Log Reader Agent from Management Studio</span></span>  
  
1.  <span data-ttu-id="507bd-115">Conéctese al publicador en [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]y expanda el nodo de servidor y la carpeta **Replicación** .</span><span class="sxs-lookup"><span data-stu-id="507bd-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node and the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="507bd-116">Expanda la carpeta **Publicaciones locales** y haga clic con el botón secundario en una publicación.</span><span class="sxs-lookup"><span data-stu-id="507bd-116">Expand the **Local Publications** folder, and then right-click a publication.</span></span>  
  
3.  <span data-ttu-id="507bd-117">Haga clic en **Ver estado del Agente de instantáneas** o **Ver estado del Agente de registro del LOG**.</span><span class="sxs-lookup"><span data-stu-id="507bd-117">Click **View Snapshot Agent Status** or **View Log Reader Agent Status**.</span></span>  
  
4.  <span data-ttu-id="507bd-118">Haga clic en **Iniciar** o **Detener**.</span><span class="sxs-lookup"><span data-stu-id="507bd-118">Click **Start** or **Stop**.</span></span>  
  
### <a name="to-start-and-stop-a-queue-reader-agent-from-management-studio"></a><span data-ttu-id="507bd-119">Para iniciar y detener un Agente de lectura de cola desde Management Studio</span><span class="sxs-lookup"><span data-stu-id="507bd-119">To start and stop a Queue Reader Agent from Management Studio</span></span>  
  
1.  <span data-ttu-id="507bd-120">Conéctese al distribuidor en [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]y expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="507bd-120">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="507bd-121">Expanda la carpeta **Agente SQL Server** y a continuación la carpeta **Trabajos** .</span><span class="sxs-lookup"><span data-stu-id="507bd-121">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="507bd-122">Haga clic con el botón secundario en el trabajo del agente y, a continuación, haga clic en **Iniciar trabajo** o **Detener trabajo**.</span><span class="sxs-lookup"><span data-stu-id="507bd-122">Right-click the job for the agent, and then click **Start Job** or **Stop Job**.</span></span> <span data-ttu-id="507bd-123">El nombre del trabajo del Agente de lectura de cola tiene el formato **[\<Distributor>].\<integer>** .</span><span class="sxs-lookup"><span data-stu-id="507bd-123">The name of the job for the Queue Reader Agent is in the form **[\<Distributor>].\<integer>**.</span></span>  
  
### <a name="to-start-and-stop-a-snapshot-agent-log-reader-agent-or-queue-reader-agent-from-replication-monitor"></a><span data-ttu-id="507bd-124">Para iniciar y detener un agente de instantáneas, un Agente de registro del LOG o un Agente de lectura de cola desde el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="507bd-124">To start and stop a Snapshot Agent, Log Reader Agent, or Queue Reader Agent from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="507bd-125">Expanda un grupo de publicador en el panel izquierdo, expanda un publicador y, a continuación, haga clic en una publicación.</span><span class="sxs-lookup"><span data-stu-id="507bd-125">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="507bd-126">Haga clic en la pestaña **Agentes** .</span><span class="sxs-lookup"><span data-stu-id="507bd-126">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="507bd-127">Haga clic con el botón secundario en un agente y, a continuación, haga clic en **Iniciar agente** o **Detener agente**.</span><span class="sxs-lookup"><span data-stu-id="507bd-127">Right-click an agent, and then click **Start Agent** or **Stop Agent**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="507bd-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="507bd-128">See Also</span></span>  
 <span data-ttu-id="507bd-129">[Monitoring Replication](../monitoring-replication.md)  (Supervisar la replicación)</span><span class="sxs-lookup"><span data-stu-id="507bd-129">[Monitoring Replication](../monitoring-replication.md) </span></span>  
 <span data-ttu-id="507bd-130">[Conceptos de los ejecutables del Agente de replicación](../concepts/replication-agent-executables-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="507bd-130">[Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) </span></span>  
 [<span data-ttu-id="507bd-131">Información general sobre los agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="507bd-131">Replication Agents Overview</span></span>](replication-agents-overview.md)  
  
  
