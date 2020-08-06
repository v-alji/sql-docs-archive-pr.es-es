---
title: Información general de la interfaz del Monitor de replicación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor
- Replication Monitor, about Replication Monitor
ms.assetid: 078f0e34-7153-45c4-8725-778b5bef88da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d9b7edbd76153f23168ec9bcf4a286d5f7cbe9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670927"
---
# <a name="overview-of-the-replication-monitor-interface"></a><span data-ttu-id="62661-102">Información general de la interfaz del Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="62661-102">Overview of the Replication Monitor Interface</span></span>
  <span data-ttu-id="62661-103">El Monitor de replicación de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] presenta una vista centrada en el publicador o en el distribuidor de toda la actividad de replicación en un formato de dos paneles.</span><span class="sxs-lookup"><span data-stu-id="62661-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor presents a Publisher-focused view or Distributor-focused view of all replication activity in a two pane format.</span></span> <span data-ttu-id="62661-104">Se agrega un publicador al monitor en el panel izquierdo y, en el panel derecho, el monitor muestra información sobre el publicador, sus publicaciones, las suscripciones a esas publicaciones y los diversos agentes de replicación.</span><span class="sxs-lookup"><span data-stu-id="62661-104">You add a Publisher to the monitor in the left pane, and in the right pane the monitor displays information on the Publisher, its publications, the subscriptions to those publications, and the various replication agents.</span></span> <span data-ttu-id="62661-105">Además de presentar información de la topología de replicación, el Monitor de replicación permite realizar varias tareas, como iniciar y detener agentes y validar datos.</span><span class="sxs-lookup"><span data-stu-id="62661-105">In addition to presenting information for the replication topology, Replication Monitor allows you to perform a number of tasks, such as starting and stopping agents, and validating data.</span></span>  
  
## <a name="viewing-information-for-the-entire-topology"></a><span data-ttu-id="62661-106">Ver información de toda la topología</span><span class="sxs-lookup"><span data-stu-id="62661-106">Viewing Information for the Entire Topology</span></span>  
 <span data-ttu-id="62661-107">El panel izquierdo del Monitor de replicación muestra</span><span class="sxs-lookup"><span data-stu-id="62661-107">The left pane of Replication Monitor displays</span></span>  
  
-   <span data-ttu-id="62661-108">Grupos de publicadores, publicadores y publicaciones.</span><span class="sxs-lookup"><span data-stu-id="62661-108">Publisher groups, Publishers, and publications.</span></span>  
  
-   <span data-ttu-id="62661-109">Distribuidores, publicadores y publicaciones.</span><span class="sxs-lookup"><span data-stu-id="62661-109">Distributors, Publishers, and publications.</span></span>  
  
 <span data-ttu-id="62661-110">Para ver cualquier información en el Monitor de replicación, primero debe agregar un publicador.</span><span class="sxs-lookup"><span data-stu-id="62661-110">To view any information in Replication Monitor, you must first add a Publisher.</span></span> <span data-ttu-id="62661-111">Para obtener más información, vea [Agregar y quitar publicadores del Monitor de replicación](add-and-remove-publishers-from-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="62661-111">For more information, see [Add and Remove Publishers from Replication Monitor](add-and-remove-publishers-from-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="62661-112">El panel izquierdo ayuda a responder a las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="62661-112">The left pane helps answer the following questions:</span></span>  
  
-   <span data-ttu-id="62661-113">¿Es correcto el sistema de replicación?</span><span class="sxs-lookup"><span data-stu-id="62661-113">Is my replication system healthy?</span></span>  
  
     <span data-ttu-id="62661-114">El estado del sistema de replicación es relativamente correcto si no existen iconos de error en los nodos del panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="62661-114">The replication system is relatively healthy if there are no error icons on nodes in the left pane.</span></span> <span data-ttu-id="62661-115">Para obtener una vista más completa del estado del sistema, también debe comprobar la pestaña **Lista de supervisión de suscripciones** , en la que se muestra información sobre las suscripciones que pueden requerir atención.</span><span class="sxs-lookup"><span data-stu-id="62661-115">To get a more complete view of system health, you should also check the **Subscription Watch List** tab, which displays information on subscriptions that might require attention.</span></span>  
  
-   <span data-ttu-id="62661-116">¿Por qué no se ejecuta un agente?</span><span class="sxs-lookup"><span data-stu-id="62661-116">Why is an agent not running?</span></span>  
  
     <span data-ttu-id="62661-117">Un agente no funciona en un momento determinado porque no está programado para ejecutarse o porque se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="62661-117">An agent is not running at a particular time either because it is not scheduled to run or because an error has occurred.</span></span> <span data-ttu-id="62661-118">Si se ha producido un error, se muestra un icono de error en los nodos correspondientes del panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="62661-118">If an error has occurred, an error icon is displayed on the appropriate nodes in the left pane.</span></span> <span data-ttu-id="62661-119">Por ejemplo, si el Agente de instantáneas de una publicación se detiene debido a un error, se muestra un icono de error en el grupo de publicador, el publicador y los nodos de publicación.</span><span class="sxs-lookup"><span data-stu-id="62661-119">For example, if the Snapshot Agent for a publication stopped because of an error, an error icon is displayed on the Publisher group, Publisher, and publication nodes.</span></span> <span data-ttu-id="62661-120">En la pestaña **Agentes** de la publicación se muestra información resumida del Agente de instantáneas; haga doble clic en el Agente de instantáneas de esta pestaña para obtener información detallada del error.</span><span class="sxs-lookup"><span data-stu-id="62661-120">Summary information for the Snapshot Agent is displayed on the **Agents** tab for the publication; double click the Snapshot Agent on this tab for detailed error information.</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-distributors"></a><span data-ttu-id="62661-121">Ver información y realizar tareas relacionadas con distribuidores</span><span class="sxs-lookup"><span data-stu-id="62661-121">Viewing Information and Performing Tasks Related to Distributors</span></span>  
 <span data-ttu-id="62661-122">El Monitor de replicación muestra información sobre distribuidores en tres pestañas:</span><span class="sxs-lookup"><span data-stu-id="62661-122">Replication Monitor displays information about Distributors on three tabs:</span></span>  
  
-   <span data-ttu-id="62661-123">Pestaña**Publicaciones**</span><span class="sxs-lookup"><span data-stu-id="62661-123">**Publications** tab</span></span>  
  
     <span data-ttu-id="62661-124">Esta pestaña proporciona información resumida de todas las publicaciones de un distribuidor.</span><span class="sxs-lookup"><span data-stu-id="62661-124">This tab provides summary information for all publications of a Distributor.</span></span>  
  
-   <span data-ttu-id="62661-125">Pestaña**Lista de supervisión de suscripciones**</span><span class="sxs-lookup"><span data-stu-id="62661-125">**Subscription Watch List** tab</span></span>  
  
     <span data-ttu-id="62661-126">Esta pestaña proporciona información sobre las suscripciones del distribuidor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="62661-126">This tab provides information about subscriptions for the selected Distributor.</span></span> <span data-ttu-id="62661-127">Puede filtrar la lista de suscripciones para ver errores, advertencias y las suscripciones que tienen un rendimiento bajo.</span><span class="sxs-lookup"><span data-stu-id="62661-127">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="62661-128">La pestaña le permite igualmente realizar las siguientes tareas: acceder a las propiedades de la suscripción, acceder a información detallada sobre el agente o agentes asociados con una suscripción, así como reinicializar y validar suscripciones.</span><span class="sxs-lookup"><span data-stu-id="62661-128">The tab also lets you to perform the following tasks: access subscription properties, access detailed information about the agent or agents associated with a subscription, reinitialize subscriptions, and validate subscriptions.</span></span>  
  
     <span data-ttu-id="62661-129">La pestaña **Lista de supervisión de suscripciones** ayuda a responder a las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="62661-129">The **Subscription Watch List** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="62661-130">¿Qué suscripciones son lentas?</span><span class="sxs-lookup"><span data-stu-id="62661-130">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="62661-131">Establezca opciones en esta pestaña para que la cuadrícula muestre las suscripciones ordenadas por su rendimiento relativo.</span><span class="sxs-lookup"><span data-stu-id="62661-131">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="62661-132">¿Es correcto el sistema de replicación?</span><span class="sxs-lookup"><span data-stu-id="62661-132">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="62661-133">La cuadrícula de esta pestaña muestra iconos de advertencia y error en las suscripciones que requieran su atención.</span><span class="sxs-lookup"><span data-stu-id="62661-133">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
     <span data-ttu-id="62661-134">Esta pestaña no está disponible para distribuidores que ejecuten versiones de [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] o anterior.</span><span class="sxs-lookup"><span data-stu-id="62661-134">This tab is not available for Distributors that are running versions of [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or earlier.</span></span>  
  
-   <span data-ttu-id="62661-135">Pestaña**Agentes**</span><span class="sxs-lookup"><span data-stu-id="62661-135">**Agents** tab</span></span>  
  
     <span data-ttu-id="62661-136">Esta pestaña muestra información detallada sobre los agentes y trabajos utilizados por todos los tipos de replicación.</span><span class="sxs-lookup"><span data-stu-id="62661-136">This tab displays detailed information about the agents and jobs that are used by all types of replication.</span></span> <span data-ttu-id="62661-137">La pestaña también le permite iniciar y detener cada agente y trabajo.</span><span class="sxs-lookup"><span data-stu-id="62661-137">The tab also let you start and stop each agent and job.</span></span>  
  
 <span data-ttu-id="62661-138">El Monitor de replicación también proporciona un menú contextual para el nodo de distribuidor.</span><span class="sxs-lookup"><span data-stu-id="62661-138">Replication Monitor also provides a context menu for the Distributor node.</span></span> <span data-ttu-id="62661-139">Haga clic con el botón secundario en un distribuidor del panel izquierdo con el fin de realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="62661-139">Right-click a Distributor in the left pane to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="62661-140">Agregar un publicador al Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="62661-140">Add a Publisher to Replication Monitor.</span></span>  
  
-   <span data-ttu-id="62661-141">Editar la configuración del Monitor de replicación del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="62661-141">Edit Replication Monitor settings for the Distributor.</span></span>  
  
-   <span data-ttu-id="62661-142">Cambiar a la vista de grupo de publicador.</span><span class="sxs-lookup"><span data-stu-id="62661-142">Switch to the Publisher Group view.</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-publishers"></a><span data-ttu-id="62661-143">Ver información y realizar tareas relacionadas con publicadores</span><span class="sxs-lookup"><span data-stu-id="62661-143">Viewing Information and Performing Tasks Related to Publishers</span></span>  
 <span data-ttu-id="62661-144">El Monitor de replicación muestra información sobre publicadores en tres pestañas:</span><span class="sxs-lookup"><span data-stu-id="62661-144">Replication Monitor displays information about Publishers on three tabs:</span></span>  
  
-   <span data-ttu-id="62661-145">Pestaña**Publicaciones**</span><span class="sxs-lookup"><span data-stu-id="62661-145">**Publications** tab</span></span>  
  
     <span data-ttu-id="62661-146">Esta pestaña proporciona información resumida de todas las publicaciones en un publicador.</span><span class="sxs-lookup"><span data-stu-id="62661-146">This tab provides summary information for all publications at a Publisher.</span></span>  
  
-   <span data-ttu-id="62661-147">Pestaña**Lista de supervisión de suscripciones**</span><span class="sxs-lookup"><span data-stu-id="62661-147">**Subscription Watch List** tab</span></span>  
  
     <span data-ttu-id="62661-148">Esta pestaña está diseñada para mostrar información sobre suscripciones de todas las publicaciones disponibles en el publicador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="62661-148">This tab is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="62661-149">Puede filtrar la lista de suscripciones para ver errores, advertencias y las suscripciones que tienen un rendimiento bajo.</span><span class="sxs-lookup"><span data-stu-id="62661-149">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="62661-150">La pestaña le permite igualmente: tener acceso a las propiedades de la suscripción, tener acceso a información detallada sobre el agente o agentes asociados con una suscripción, y reinicializar y validar suscripciones.</span><span class="sxs-lookup"><span data-stu-id="62661-150">The tab also allows you to: access subscription properties; access detailed information about the agent or agents associated with a subscription; reinitialize subscriptions; and validate subscriptions.</span></span>  
  
     <span data-ttu-id="62661-151">La pestaña **Lista de supervisión de suscripciones** ayuda a responder a las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="62661-151">The **Subscription Watch List** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="62661-152">¿Qué suscripciones son lentas?</span><span class="sxs-lookup"><span data-stu-id="62661-152">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="62661-153">Establezca opciones en esta pestaña para que la cuadrícula muestre las suscripciones ordenadas por su rendimiento relativo.</span><span class="sxs-lookup"><span data-stu-id="62661-153">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="62661-154">¿Es correcto el sistema de replicación?</span><span class="sxs-lookup"><span data-stu-id="62661-154">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="62661-155">La cuadrícula de esta pestaña muestra iconos de advertencia y error en las suscripciones que requieran su atención.</span><span class="sxs-lookup"><span data-stu-id="62661-155">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
     <span data-ttu-id="62661-156">Esta pestaña no se muestra en los distribuidores que ejecuten versiones anteriores a [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62661-156">This tab is not displayed for Distributors running versions prior to [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span>  
  
-   <span data-ttu-id="62661-157">Pestaña**Agentes**</span><span class="sxs-lookup"><span data-stu-id="62661-157">**Agents** tab</span></span>  
  
     <span data-ttu-id="62661-158">Esta pestaña muestra información detallada sobre los agentes y trabajos utilizados por todos los tipos de replicación.</span><span class="sxs-lookup"><span data-stu-id="62661-158">This tab displays detailed information about the agents and jobs used by all types of replication.</span></span> <span data-ttu-id="62661-159">La pestaña también le permite iniciar y detener cada agente y trabajo.</span><span class="sxs-lookup"><span data-stu-id="62661-159">The tab also allows you to start and stop each agent and job.</span></span>  
  
 <span data-ttu-id="62661-160">Para más información, vea [Visualización de información y realización de tareas mediante el Monitor de replicación](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="62661-160">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="62661-161">El Monitor de replicación también proporciona un menú contextual para el nodo de publicador.</span><span class="sxs-lookup"><span data-stu-id="62661-161">Replication Monitor also provides a context menu for the Publisher node.</span></span> <span data-ttu-id="62661-162">En el panel izquierdo, haga clic con el botón secundario en un publicador para:</span><span class="sxs-lookup"><span data-stu-id="62661-162">Right-click a Publisher in the left pane to:</span></span>  
  
-   <span data-ttu-id="62661-163">Editar la configuración del Monitor de replicación para el publicador.</span><span class="sxs-lookup"><span data-stu-id="62661-163">Edit Replication Monitor settings for the Publisher</span></span>  
  
-   <span data-ttu-id="62661-164">Quitar el publicador del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="62661-164">Remove the Publisher from Replication Monitor</span></span>  
  
-   <span data-ttu-id="62661-165">Ver y editar perfiles de agente.</span><span class="sxs-lookup"><span data-stu-id="62661-165">View and edit agent profiles</span></span>  
  
-   <span data-ttu-id="62661-166">Conectarse o desconectarse del distribuidor que almacena información sobre el publicador.</span><span class="sxs-lookup"><span data-stu-id="62661-166">Connect to or disconnect from the Distributor that stores information about the Publisher</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-publications"></a><span data-ttu-id="62661-167">Ver información y realizar tareas relacionadas con publicaciones</span><span class="sxs-lookup"><span data-stu-id="62661-167">Viewing Information and Performing Tasks Related to Publications</span></span>  
 <span data-ttu-id="62661-168">El Monitor de replicación muestra información sobre publicaciones en tres pestañas y varias ventanas de detalles:</span><span class="sxs-lookup"><span data-stu-id="62661-168">Replication Monitor displays information about publications on three tabs and a number of detail windows:</span></span>  
  
-   <span data-ttu-id="62661-169">Pestaña**Todas las suscripciones**</span><span class="sxs-lookup"><span data-stu-id="62661-169">**All Subscriptions** tab</span></span>  
  
     <span data-ttu-id="62661-170">En esta pestaña se muestra información acerca de todas las suscripciones de la publicación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="62661-170">This tab displays information about all subscriptions to the selected publication.</span></span> <span data-ttu-id="62661-171">De forma predeterminada, esta pestaña está ordenada por orden de prioridad: primero los errores, a continuación las advertencias y, por último, en orden creciente de rendimiento, las suscripciones con rendimiento bajo en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="62661-171">By default, this tab is sorted in priority order: errors, then warnings, then in increasing order of performance, with any poorly performing subscriptions at the top.</span></span>  
  
     <span data-ttu-id="62661-172">La pestaña **Todas las suscripciones** ayuda a responder a las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="62661-172">The **All Subscriptions** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="62661-173">¿Qué suscripciones son lentas?</span><span class="sxs-lookup"><span data-stu-id="62661-173">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="62661-174">Establezca opciones en esta pestaña para que la cuadrícula muestre las suscripciones ordenadas por su rendimiento relativo.</span><span class="sxs-lookup"><span data-stu-id="62661-174">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="62661-175">¿Es correcto el sistema de replicación?</span><span class="sxs-lookup"><span data-stu-id="62661-175">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="62661-176">La cuadrícula de esta pestaña muestra iconos de advertencia y error en las suscripciones que requieran su atención.</span><span class="sxs-lookup"><span data-stu-id="62661-176">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
-   <span data-ttu-id="62661-177">Pestaña**Agentes**</span><span class="sxs-lookup"><span data-stu-id="62661-177">**Agents** tab</span></span>  
  
     <span data-ttu-id="62661-178">En esta pestaña se muestra información sobre los agentes utilizados por la replicación.</span><span class="sxs-lookup"><span data-stu-id="62661-178">This tab displays information about the agents that are used by replication.</span></span> <span data-ttu-id="62661-179">Esta pestaña muestra información de los siguientes agentes:</span><span class="sxs-lookup"><span data-stu-id="62661-179">This tab displays information about the following agents:</span></span>  
  
    -   <span data-ttu-id="62661-180">El Agente de instantáneas, utilizado por todas las publicaciones.</span><span class="sxs-lookup"><span data-stu-id="62661-180">The Snapshot Agent, which is used by all publications.</span></span>  
  
    -   <span data-ttu-id="62661-181">El Agente de registro del LOG, utilizado por todas las publicaciones transaccionales.</span><span class="sxs-lookup"><span data-stu-id="62661-181">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
    -   <span data-ttu-id="62661-182">El Agente de lectura de cola, utilizado por las publicaciones transaccionales con suscripciones de actualización en cola habilitadas.</span><span class="sxs-lookup"><span data-stu-id="62661-182">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
     <span data-ttu-id="62661-183">La pestaña también permite realizar las tareas siguientes: tener acceso a información detallada sobre cada agente e iniciar y detener cada agente.</span><span class="sxs-lookup"><span data-stu-id="62661-183">The tab also allows for you to perform the following tasks: access detailed information about each agent, and start and stop each agent.</span></span> <span data-ttu-id="62661-184">Para obtener información sobre los agentes asociados con suscripciones (el Agente de distribución y el Agente de mezcla), vea la sección "Ver información y realizar tareas relacionadas con suscripciones" en este tema.</span><span class="sxs-lookup"><span data-stu-id="62661-184">For information about agents that are associated with subscriptions (the Distribution Agent and Merge Agent), see the section "Viewing Information and Performing Tasks Related to Subscriptions" in this topic.</span></span>  
  
-   <span data-ttu-id="62661-185">Pestaña**Advertencias**</span><span class="sxs-lookup"><span data-stu-id="62661-185">**Warnings** tab</span></span>  
  
     <span data-ttu-id="62661-186">Esta pestaña le permite especificar advertencias y alertas para los agentes.</span><span class="sxs-lookup"><span data-stu-id="62661-186">This tab enables you to specify warnings and alerts for agents.</span></span> <span data-ttu-id="62661-187">Para más información, consulte [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="62661-187">For more information, see [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="62661-188">Pestaña**Testigos de seguimiento** (solo replicación transaccional)</span><span class="sxs-lookup"><span data-stu-id="62661-188">**Tracer Tokens** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="62661-189">Esta pestaña permite medir la latencia, es decir, el tiempo que transcurre entre la confirmación de una transacción en el publicador y la confirmación de la transacción correspondiente en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="62661-189">This tab allows you to measure latency, the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span>  
  
     <span data-ttu-id="62661-190">Esta pestaña ayuda a responder a la siguiente pregunta:</span><span class="sxs-lookup"><span data-stu-id="62661-190">This tab helps answers the following question:</span></span>  
  
    -   <span data-ttu-id="62661-191">¿Cuánto tardará una transacción confirmada ahora en llegar al suscriptor en la replicación transaccional?</span><span class="sxs-lookup"><span data-stu-id="62661-191">How long will it take a transaction committed now to reach a Subscriber in transactional replication?</span></span>  
  
         <span data-ttu-id="62661-192">Vea el tiempo total que tarda una transacción en viajar por el sistema y compárelo también con tiempos anteriores.</span><span class="sxs-lookup"><span data-stu-id="62661-192">View the total time for a transaction to travel through the system and also compare it to previous times.</span></span>  
  
     <span data-ttu-id="62661-193">Esta pestaña no se muestra para los distribuidores que ejecuten [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] o anterior.</span><span class="sxs-lookup"><span data-stu-id="62661-193">This tab is not displayed for Distributors running [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or earlier.</span></span> <span data-ttu-id="62661-194">Para obtener más información sobre cómo utilizar los testigos de seguimiento, vea [Medir la latencia y validar las conexiones de la replicación transaccional](measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="62661-194">For more information on tracer tokens, see [Measure Latency and Validate Connections for Transactional Replication](measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="62661-195">Ventanas de detalles para los agentes asociados con una publicación.</span><span class="sxs-lookup"><span data-stu-id="62661-195">Detail windows for the agents associated with a publication.</span></span> <span data-ttu-id="62661-196">Los siguientes agentes están asociados con publicaciones:</span><span class="sxs-lookup"><span data-stu-id="62661-196">The following agents are associated with publications:</span></span>  
  
    -   <span data-ttu-id="62661-197">El Agente de instantáneas, utilizado por todas las publicaciones.</span><span class="sxs-lookup"><span data-stu-id="62661-197">The Snapshot Agent, which is used by all publications.</span></span>  
  
    -   <span data-ttu-id="62661-198">El Agente de registro del LOG, utilizado por todas las publicaciones transaccionales.</span><span class="sxs-lookup"><span data-stu-id="62661-198">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
    -   <span data-ttu-id="62661-199">El Agente de lectura de cola, utilizado por las publicaciones transaccionales con suscripciones de actualización en cola habilitadas.</span><span class="sxs-lookup"><span data-stu-id="62661-199">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
     <span data-ttu-id="62661-200">Haga doble clic en un agente en el Monitor de replicación para tener acceso a información en la ventana de detalles.</span><span class="sxs-lookup"><span data-stu-id="62661-200">Double-click an agent in Replication Monitor to access information in a detail window.</span></span> <span data-ttu-id="62661-201">Además de los agentes mencionados anteriormente, hay agentes asociados con suscripciones: el Agente de distribución para suscripciones a instantánea y publicaciones transaccionales, y el agente de mezcla para suscripciones a publicaciones de combinación.</span><span class="sxs-lookup"><span data-stu-id="62661-201">In addition to the agents listed above, there are agents associated with subscriptions: the Distribution Agent for subscriptions to snapshot and transactional publications; and the Merge Agent for subscriptions to merge publications.</span></span> <span data-ttu-id="62661-202">Para obtener más información, vea la sección "Ver información y realizar tareas relacionadas con suscripciones" en este tema.</span><span class="sxs-lookup"><span data-stu-id="62661-202">For more information, see the section "Viewing Information and Performing Tasks Related to Subscriptions" in this topic.</span></span>  
  
     <span data-ttu-id="62661-203">Las ventanas de detalles de agente proporcionan información sobre las sesiones del agente, incluida la hora de inicio, la hora de finalización, la duración y las acciones realizadas en una sesión.</span><span class="sxs-lookup"><span data-stu-id="62661-203">The agent detail windows provide information about agent sessions, including start time, end time, duration, and the actions performed in a session.</span></span> <span data-ttu-id="62661-204">Ayudan a responder a la siguiente pregunta:</span><span class="sxs-lookup"><span data-stu-id="62661-204">They help to answer the following question:</span></span>  
  
    -   <span data-ttu-id="62661-205">¿Por qué no se ejecuta un agente?</span><span class="sxs-lookup"><span data-stu-id="62661-205">Why is an agent not running?</span></span>  
  
         <span data-ttu-id="62661-206">Los mensajes de error disponibles proporcionan información detallada sobre por qué no funciona un agente y un punto inicial para solucionar problemas con los agentes asociados con una publicación.</span><span class="sxs-lookup"><span data-stu-id="62661-206">The error messages available provide detailed information on why an agent is not running and provide a starting point for troubleshooting issues with the agents associated with a publication.</span></span>  
  
 <span data-ttu-id="62661-207">Para más información, vea [Visualización de información y realización de tareas mediante el Monitor de replicación](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="62661-207">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="62661-208">El Monitor de replicación también proporciona un menú contextual para el nodo de publicaciones.</span><span class="sxs-lookup"><span data-stu-id="62661-208">Replication Monitor also provides a context menu for the publications node.</span></span> <span data-ttu-id="62661-209">En el panel izquierdo, haga clic con el botón secundario en una publicación para:</span><span class="sxs-lookup"><span data-stu-id="62661-209">Right-click a publication in the left pane to:</span></span>  
  
-   <span data-ttu-id="62661-210">Reinicializar todas las suscripciones en una publicación.</span><span class="sxs-lookup"><span data-stu-id="62661-210">Reinitialize all subscriptions to a publication</span></span>  
  
-   <span data-ttu-id="62661-211">Validar todas las suscripciones en una publicación.</span><span class="sxs-lookup"><span data-stu-id="62661-211">Validate all subscriptions to a publication</span></span>  
  
-   <span data-ttu-id="62661-212">Generar una instantánea para una publicación.</span><span class="sxs-lookup"><span data-stu-id="62661-212">Generate a snapshot for a publication</span></span>  
  
-   <span data-ttu-id="62661-213">Ver y editar las propiedades de una publicación.</span><span class="sxs-lookup"><span data-stu-id="62661-213">View and edit publication properties</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-subscriptions"></a><span data-ttu-id="62661-214">Ver información y realizar tareas relacionadas con suscripciones</span><span class="sxs-lookup"><span data-stu-id="62661-214">Viewing Information and Performing Tasks Related to Subscriptions</span></span>  
 <span data-ttu-id="62661-215">El Monitor de replicación muestra información sobre suscripciones en varias pestañas diferentes.</span><span class="sxs-lookup"><span data-stu-id="62661-215">Replication Monitor displays information about subscriptions on a number of different tabs.</span></span> <span data-ttu-id="62661-216">Haga doble clic en una suscripción en el Monitor de replicación para tener acceso a estas pestañas en una ventana de detalles.</span><span class="sxs-lookup"><span data-stu-id="62661-216">Double-click a subscription in Replication Monitor to access these tabs in a detail window.</span></span> <span data-ttu-id="62661-217">Todas estas pestañas son útiles para responder a la pregunta "¿Por qué no funciona un agente?".</span><span class="sxs-lookup"><span data-stu-id="62661-217">All of the tabs are useful in answering the question "Why is an agent not running?"</span></span> <span data-ttu-id="62661-218">Los mensajes de error disponibles proporcionan información detallada sobre por qué no funciona un agente y un punto inicial para solucionar problemas con los agentes asociados con una suscripción.</span><span class="sxs-lookup"><span data-stu-id="62661-218">The error messages available provide detailed information on why an agent is not running and provide a starting point for troubleshooting issues with the agents associated with a subscription.</span></span>  
  
-   <span data-ttu-id="62661-219">**Todas las suscripciones** y **Lista de supervisión de suscripciones**</span><span class="sxs-lookup"><span data-stu-id="62661-219">**All Subscriptions tab** and **Subscription Watch List tab.**</span></span>  
  
     <span data-ttu-id="62661-220">Estas pestañas se han descrito anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="62661-220">These tabs are described earlier in this topic.</span></span>  
  
-   <span data-ttu-id="62661-221">Pestaña**Historial de Publicador a distribuidor** (solo replicación transaccional)</span><span class="sxs-lookup"><span data-stu-id="62661-221">**Publisher to Distributor History** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="62661-222">En esta pestaña se muestra información sobre el Agente de registro del LOG para una publicación (la pestaña es idéntica a la ventana de detalles del Agente de registro del LOG).</span><span class="sxs-lookup"><span data-stu-id="62661-222">This tab displays information on the Log Reader Agent for a publication (the tab is identical to the Log Reader Agent details window).</span></span>  
  
-   <span data-ttu-id="62661-223">Pestaña**Historial de Distribuidor a suscriptor** (replicación de instantánea y replicación transaccional)</span><span class="sxs-lookup"><span data-stu-id="62661-223">**Distributor to Subscriber History** tab (snapshot replication and transactional replication)</span></span>  
  
     <span data-ttu-id="62661-224">En esta pestaña se muestra información sobre el Agente de distribución para una suscripción.</span><span class="sxs-lookup"><span data-stu-id="62661-224">This tab displays information on the Distribution Agent for a subscription.</span></span>  
  
-   <span data-ttu-id="62661-225">Pestaña**Comandos sin distribuir** (solo replicación transaccional)</span><span class="sxs-lookup"><span data-stu-id="62661-225">**Undistributed Commands** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="62661-226">En esta pestaña se muestra información sobre le número de comandos de la base de datos de distribución que no se han entregado al suscriptor seleccionado y el tiempo estimado para entregar esos comandos.</span><span class="sxs-lookup"><span data-stu-id="62661-226">This tab displays information about the number of commands in the distribution database that have not been delivered to the selected Subscriber, and the estimated time to deliver those commands.</span></span> <span data-ttu-id="62661-227">La pestaña ayuda a responder a la pregunta, "¿Qué retraso tiene mi suscripción?"</span><span class="sxs-lookup"><span data-stu-id="62661-227">The tab helps answer the question, "How far behind is my subscription?"</span></span> <span data-ttu-id="62661-228">Esta pestaña no se muestra en los distribuidores que ejecuten versiones anteriores a SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="62661-228">This tab is not displayed for Distributors running versions prior to SQL Server 2005.</span></span>  
  
-   <span data-ttu-id="62661-229">Pestaña**Historial de sincronizaciones** (solo replicación de mezcla)</span><span class="sxs-lookup"><span data-stu-id="62661-229">**Synchronization History** tab (merge replication only)</span></span>  
  
     <span data-ttu-id="62661-230">En esta pestaña se muestra información sobre el Agente de mezcla para una suscripción.</span><span class="sxs-lookup"><span data-stu-id="62661-230">This tab displays information on the Merge Agent for a subscription.</span></span> <span data-ttu-id="62661-231">Esta pestaña ayuda a responder a la siguiente pregunta:</span><span class="sxs-lookup"><span data-stu-id="62661-231">This tab helps answer the following question:</span></span>  
  
    -   <span data-ttu-id="62661-232">¿Por qué es lenta la suscripción de mezcla?</span><span class="sxs-lookup"><span data-stu-id="62661-232">Why is my merge subscription slow?</span></span>  
  
         <span data-ttu-id="62661-233">En esta pestaña se proporcionan estadísticas detalladas de cada artículo procesado durante la sincronización, incluido el tiempo invertido en cada fase del proceso (carga de cambios, descarga de cambios, etc.).</span><span class="sxs-lookup"><span data-stu-id="62661-233">This tab provides detailed statistics for each article processed during synchronization, including the amount of time spent in each processing phase (uploading changes, downloading changes, and so on).</span></span> <span data-ttu-id="62661-234">Puede ayudar a identificar con precisión tablas específicas que provocan lentitud y el mejor lugar para solucionar problemas de rendimiento con suscripciones de mezcla.</span><span class="sxs-lookup"><span data-stu-id="62661-234">It can help pinpoint specific tables that are causing slowdowns and is the best place to troubleshoot performance issues with merge subscriptions.</span></span>  
  
 <span data-ttu-id="62661-235">Para más información, vea [Visualización de información y realización de tareas mediante el Monitor de replicación](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="62661-235">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>
  
## <a name="viewing-information-and-performing-tasks-related-to-agent-profiles"></a><span data-ttu-id="62661-236">Ver información y realizar tareas relacionadas con perfiles de agente</span><span class="sxs-lookup"><span data-stu-id="62661-236">Viewing Information and Performing Tasks Related to Agent Profiles</span></span>  
 <span data-ttu-id="62661-237">El Monitor de replicación incluye varios cuadros de diálogo para administrar perfiles de agente.</span><span class="sxs-lookup"><span data-stu-id="62661-237">Replication Monitor includes a number of dialog boxes for managing agent profiles.</span></span> <span data-ttu-id="62661-238">Los perfiles de agente son conjuntos de parámetros de un agente que determinan su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="62661-238">Agent profiles are sets of parameters for an agent that determine agent behavior.</span></span> <span data-ttu-id="62661-239">Para obtener más información, consulte [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="62661-239">For more information, see [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span></span> <span data-ttu-id="62661-240">Los cuadros de diálogo son:</span><span class="sxs-lookup"><span data-stu-id="62661-240">The dialog boxes are:</span></span>  
  
-   <span data-ttu-id="62661-241">**Perfiles de agente**</span><span class="sxs-lookup"><span data-stu-id="62661-241">**Agent Profiles**</span></span>  
  
     <span data-ttu-id="62661-242">Este cuadro de diálogo permite: cambiar las propiedades de perfiles, crear y eliminar perfiles, especificar un perfil predeterminado y especificar que todos los agentes de un tipo específico (por ejemplo, los Agentes de instantáneas) deben utilizar un perfil determinado.</span><span class="sxs-lookup"><span data-stu-id="62661-242">This dialog box allows you to: change the properties of profiles; create and delete profiles; specify a default profile; and specify that all agents of a specific type (such as Snapshot Agents) should use a given profile.</span></span>  
  
-   <span data-ttu-id="62661-243">**Propiedades de \<AgentProfileName>**</span><span class="sxs-lookup"><span data-stu-id="62661-243">**\<AgentProfileName> Properties**</span></span>  
  
     <span data-ttu-id="62661-244">Este cuadro de diálogo permite ver y editar la configuración de parámetros de un perfil.</span><span class="sxs-lookup"><span data-stu-id="62661-244">This dialog box allows you to view and edit the parameter settings in a profile.</span></span>  
  
-   <span data-ttu-id="62661-245">**Nuevo perfil de agente**</span><span class="sxs-lookup"><span data-stu-id="62661-245">**New Agent Profile**</span></span>  
  
     <span data-ttu-id="62661-246">Este cuadro de diálogo permite crear un perfil nuevo y, opcionalmente, incluye los valores de un perfil existente.</span><span class="sxs-lookup"><span data-stu-id="62661-246">This dialog box allows you to create a new profile, optionally including the values from an existing profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62661-247">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62661-247">See Also</span></span>  
 [<span data-ttu-id="62661-248">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="62661-248">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
