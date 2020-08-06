---
title: Ver y modificar parámetros del símbolo del sistema del agente de replicación (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], command prompt parameters
ms.assetid: 45f2e781-c21d-4b44-8992-89f60fb3d022
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 752f674c21bb66c7b64e399e30e4917512431195
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663413"
---
# <a name="view-and-modify-replication-agent-command-prompt-parameters-sql-server-management-studio"></a><span data-ttu-id="11e3d-102">Ver y modificar parámetros del símbolo del sistema de los agentes de replicación (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="11e3d-102">View and Modify Replication Agent Command Prompt Parameters (SQL Server Management Studio)</span></span>
  <span data-ttu-id="11e3d-103">Los agentes de replicación son ejecutables que aceptan parámetros en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="11e3d-103">Replication agents are executables that accept command line parameters.</span></span> <span data-ttu-id="11e3d-104">De forma predeterminada, los agentes se ejecutan en los pasos de trabajo del Agente [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], por lo que estos parámetros se pueden ver y modificar en el cuadro de diálogo **Propiedades del trabajo - \<Job>** .</span><span class="sxs-lookup"><span data-stu-id="11e3d-104">By default, agents run under [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job steps, so these parameters can be viewed and modified using the **Job Properties - \<Job>** dialog box.</span></span> <span data-ttu-id="11e3d-105">Este cuadro de diálogo está disponible en la carpeta **Trabajos** en [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] y en la pestaña **Agentes** en el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="11e3d-105">This dialog box is available from the **Jobs** folder in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from the **Agents** tab in Replication Monitor.</span></span> <span data-ttu-id="11e3d-106">Para información sobre cómo iniciar el Monitor de replicación, vea [Iniciar el Monitor de replicación](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="11e3d-106">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11e3d-107">Los cambios en los parámetros del agente tendrán efecto la próxima vez que se inicie el agente.</span><span class="sxs-lookup"><span data-stu-id="11e3d-107">Agent parameter changes take effect the next time the agent is started.</span></span> <span data-ttu-id="11e3d-108">Si el agente se ejecuta sin interrupción, debe detenerlo y reiniciarlo.</span><span class="sxs-lookup"><span data-stu-id="11e3d-108">If the agent runs continuously, you must stop and restart the agent.</span></span>  
  
 <span data-ttu-id="11e3d-109">Aunque los parámetros se pueden modificar directamente, es más habitual modificarlos mediante un perfil de agente.</span><span class="sxs-lookup"><span data-stu-id="11e3d-109">Although parameters can be modified directly, it is more common to modify them through an agent profile.</span></span> <span data-ttu-id="11e3d-110">Para obtener más información, consulte [Replication Agent Profiles](replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="11e3d-110">For more information, see [Replication Agent Profiles](replication-agent-profiles.md).</span></span>  
  
 <span data-ttu-id="11e3d-111">Si tiene acceso a trabajos de agente en la carpeta **Trabajos** , utilice la siguiente tabla para determinar el nombre del trabajo del agente y los parámetros disponibles para cada agente.</span><span class="sxs-lookup"><span data-stu-id="11e3d-111">If you access agent jobs from the **Jobs** folder, use the following table to determine the agent job name and the parameters available for each agent.</span></span>  
  
|<span data-ttu-id="11e3d-112">Agente</span><span class="sxs-lookup"><span data-stu-id="11e3d-112">Agent</span></span>|<span data-ttu-id="11e3d-113">Nombre del trabajo</span><span class="sxs-lookup"><span data-stu-id="11e3d-113">Job name</span></span>|<span data-ttu-id="11e3d-114">Para obtener una lista de parámetros, vea...</span><span class="sxs-lookup"><span data-stu-id="11e3d-114">For a list of parameters, see...</span></span>|  
|-----------|--------------|------------------------------------|  
|<span data-ttu-id="11e3d-115">Agente de instantáneas</span><span class="sxs-lookup"><span data-stu-id="11e3d-115">Snapshot Agent</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<integer>**|[<span data-ttu-id="11e3d-116">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="11e3d-116">Replication Snapshot Agent</span></span>](replication-snapshot-agent.md)|  
|<span data-ttu-id="11e3d-117">Agente de replicación para una partición de publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="11e3d-117">Snapshot Agent for a merge publication partition</span></span>|<span data-ttu-id="11e3d-118">**Dyn_\<Publisher>-\<PublicationDatabase>-\<Publication>-\<GUID>**</span><span class="sxs-lookup"><span data-stu-id="11e3d-118">**Dyn_\<Publisher>-\<PublicationDatabase>-\<Publication>-\<GUID>**</span></span>|[<span data-ttu-id="11e3d-119">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="11e3d-119">Replication Snapshot Agent</span></span>](replication-snapshot-agent.md)|  
|<span data-ttu-id="11e3d-120">Agente de registro del LOG</span><span class="sxs-lookup"><span data-stu-id="11e3d-120">Log Reader Agent</span></span>|**\<Publisher>-\<PublicationDatabase>-\<integer>**|[<span data-ttu-id="11e3d-121">Agente de registro del LOG de replicación</span><span class="sxs-lookup"><span data-stu-id="11e3d-121">Replication Log Reader Agent</span></span>](replication-log-reader-agent.md)|  
|<span data-ttu-id="11e3d-122">Agente de mezcla para suscripciones de extracción</span><span class="sxs-lookup"><span data-stu-id="11e3d-122">Merge Agent for pull subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<integer>**|[<span data-ttu-id="11e3d-123">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="11e3d-123">Replication Merge Agent</span></span>](replication-merge-agent.md)|  
|<span data-ttu-id="11e3d-124">Agente de mezcla para suscripciones de inserción</span><span class="sxs-lookup"><span data-stu-id="11e3d-124">Merge Agent for push subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|[<span data-ttu-id="11e3d-125">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="11e3d-125">Replication Merge Agent</span></span>](replication-merge-agent.md)|  
|<span data-ttu-id="11e3d-126">Agente de distribución para suscripciones de inserción</span><span class="sxs-lookup"><span data-stu-id="11e3d-126">Distribution Agent for push subscriptions</span></span>|<span data-ttu-id="11e3d-127">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="11e3d-127">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span></span>|[<span data-ttu-id="11e3d-128">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="11e3d-128">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="11e3d-129">Agente de distribución para suscripciones de extracción</span><span class="sxs-lookup"><span data-stu-id="11e3d-129">Distribution Agent for pull subscriptions</span></span>|<span data-ttu-id="11e3d-130">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="11e3d-130">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span></span>|[<span data-ttu-id="11e3d-131">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="11e3d-131">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="11e3d-132">Agente de distribución para suscripciones de inserción en suscriptores que no sean de SQL Server</span><span class="sxs-lookup"><span data-stu-id="11e3d-132">Distribution Agent for push subscriptions to non-SQL Server Subscribers</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|[<span data-ttu-id="11e3d-133">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="11e3d-133">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="11e3d-134">Agente de lectura de cola</span><span class="sxs-lookup"><span data-stu-id="11e3d-134">Queue Reader Agent</span></span>|<span data-ttu-id="11e3d-135">**[\<Distributor>].\<integer>**</span><span class="sxs-lookup"><span data-stu-id="11e3d-135">**[\<Distributor>].\<integer>**</span></span>|[<span data-ttu-id="11e3d-136">Agente de lectura de cola de replicación</span><span class="sxs-lookup"><span data-stu-id="11e3d-136">Replication Queue Reader Agent</span></span>](replication-queue-reader-agent.md)|  
  
 <span data-ttu-id="11e3d-137"><sup>1</sup> Para las suscripciones de inserción a publicaciones de Oracle, es \*\*\<Publisher>-\<Publisher**> en lugar de **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="11e3d-137"><sup>1</sup> For push subscriptions to Oracle publications, it is \*\*\<Publisher>-\<Publisher**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
 <span data-ttu-id="11e3d-138"><sup>2</sup> Para las suscripciones de extracción a publicaciones de Oracle, es \*\*\<Publisher>-\<DistributionDatabase**> en lugar de **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="11e3d-138"><sup>2</sup> For pull subscriptions to Oracle publications, it is \*\*\<Publisher>-\<DistributionDatabase**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
### <a name="to-view-and-modify-replication-agent-command-line-parameters-from-management-studio"></a><span data-ttu-id="11e3d-139">Para ver y modificar los parámetros de la línea de comandos del agente de replicación desde Management Studio</span><span class="sxs-lookup"><span data-stu-id="11e3d-139">To view and modify replication agent command line parameters from Management Studio</span></span>  
  
1.  <span data-ttu-id="11e3d-140">Conéctese al equipo adecuado en [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]y, a continuación, expanda el nodo de servidor:</span><span class="sxs-lookup"><span data-stu-id="11e3d-140">Connect to the appropriate computer in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node:</span></span>  
  
    -   <span data-ttu-id="11e3d-141">En el Agente de distribución y el Agente de mezcla para suscripciones de extracción, conéctese al suscriptor.</span><span class="sxs-lookup"><span data-stu-id="11e3d-141">For the Distribution Agent and Merge Agent for pull subscriptions, connect to the Subscriber.</span></span>  
  
    -   <span data-ttu-id="11e3d-142">Para el resto de agentes, conéctese al distribuidor.</span><span class="sxs-lookup"><span data-stu-id="11e3d-142">For all other agents, connect to the Distributor.</span></span>  
  
2.  <span data-ttu-id="11e3d-143">Expanda la carpeta **Agente SQL Server** y a continuación la carpeta **Trabajos** .</span><span class="sxs-lookup"><span data-stu-id="11e3d-143">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="11e3d-144">Haga clic con el botón derecho en un trabajo y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="11e3d-144">Right-click a job, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="11e3d-145">En la página **Pasos** del cuadro de diálogo **Propiedades del trabajo - \<Job>** , seleccione el paso **Ejecutar agente** y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="11e3d-145">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="11e3d-146">En el cuadro de diálogo **Propiedades de paso de trabajo - Ejecutar agente** , edite el campo **Comando** .</span><span class="sxs-lookup"><span data-stu-id="11e3d-146">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
6.  <span data-ttu-id="11e3d-147">Haga clic en **Aceptar** en los dos cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="11e3d-147">Click **OK** on both dialog boxes.</span></span>  
  
### <a name="to-view-and-modify-distribution-agent-and-merge-agent-command-line-parameters-from-replication-monitor"></a><span data-ttu-id="11e3d-148">Para ver y modificar los parámetros de la línea de comandos del Agente de distribución y el Agente de mezcla desde el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="11e3d-148">To view and modify Distribution Agent and Merge Agent command line parameters from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="11e3d-149">Expanda un grupo de publicador en el panel izquierdo del Monitor de replicación, expanda un publicador y, a continuación, haga clic en una publicación.</span><span class="sxs-lookup"><span data-stu-id="11e3d-149">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="11e3d-150">Haga clic en la pestaña **Todas las suscripciones** .</span><span class="sxs-lookup"><span data-stu-id="11e3d-150">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="11e3d-151">Haga clic con el botón secundario en una suscripción y, a continuación, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="11e3d-151">Right-click a subscription, and then click **View Details**.</span></span>  
  
4.  <span data-ttu-id="11e3d-152">En la **ventana \< SubscriptionName> suscripción** , haga clic en **acción**y, a continuación, haga clic en \*\* \<AgentName> propiedades del trabajo\*\*.</span><span class="sxs-lookup"><span data-stu-id="11e3d-152">In the **Subscription \< SubscriptionName>** window, click **Action**, and then click **\<AgentName> Job Properties**.</span></span>  
  
5.  <span data-ttu-id="11e3d-153">En la página **Pasos** del cuadro de diálogo **Propiedades del trabajo - \<Job>** , seleccione el paso **Ejecutar agente** y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="11e3d-153">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
6.  <span data-ttu-id="11e3d-154">En el cuadro de diálogo **Propiedades de paso de trabajo - Ejecutar agente** , edite el campo **Comando** .</span><span class="sxs-lookup"><span data-stu-id="11e3d-154">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
7.  <span data-ttu-id="11e3d-155">Haga clic en **Aceptar** en los dos cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="11e3d-155">Click **OK** on both dialog boxes.</span></span>  
  
### <a name="to-view-and-modify-snapshot-agent-log-reader-agent-and-queue-reader-agent-command-line-parameters-from-replication-monitor"></a><span data-ttu-id="11e3d-156">Para ver y modificar los parámetros de la línea de comandos del Agente de instantáneas, Agente de registro del LOG y Agente de lectura de cola desde el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="11e3d-156">To view and modify Snapshot Agent, Log Reader Agent, and Queue Reader Agent command line parameters from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="11e3d-157">Expanda un grupo de publicador en el panel izquierdo del Monitor de replicación, expanda un publicador y, a continuación, haga clic en una publicación.</span><span class="sxs-lookup"><span data-stu-id="11e3d-157">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="11e3d-158">Haga clic en la pestaña **Agentes** .</span><span class="sxs-lookup"><span data-stu-id="11e3d-158">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="11e3d-159">Haga clic con el botón secundario en un agente en la cuadrícula y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="11e3d-159">Right-click an agent in the grid, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="11e3d-160">En la página **Pasos** del cuadro de diálogo **Propiedades del trabajo - \<Job>** , seleccione el paso **Ejecutar agente** y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="11e3d-160">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="11e3d-161">En el cuadro de diálogo **Propiedades de paso de trabajo - Ejecutar agente** , edite el campo **Comando** .</span><span class="sxs-lookup"><span data-stu-id="11e3d-161">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
6.  <span data-ttu-id="11e3d-162">Haga clic en **Aceptar** en los dos cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="11e3d-162">Click **OK** on both dialog boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e3d-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11e3d-163">See Also</span></span>  
 <span data-ttu-id="11e3d-164">[Administración del Agente de replicación](replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="11e3d-164">[Replication Agent Administration](replication-agent-administration.md) </span></span>  
 <span data-ttu-id="11e3d-165">[Conceptos de los ejecutables del Agente de replicación](../concepts/replication-agent-executables-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="11e3d-165">[Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) </span></span>  
 [<span data-ttu-id="11e3d-166">Información general sobre los agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="11e3d-166">Replication Agents Overview</span></span>](replication-agents-overview.md)  
  
  
