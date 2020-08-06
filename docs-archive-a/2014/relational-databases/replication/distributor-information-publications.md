---
title: Cuadro de diálogo Replicación de SQL Server ' información del distribuidor ' | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.Distributor.Publications.f1
- sql12.rep.monitor.Distributor.commonjobs..f1
- sql12.rep.monitor.Distributor.SubscriptionSummary.merge.f1
- sql12.rep.monitor.Distributor.SubscriptionSummary.snapshot.f1
- sql12.rep.monitor.Distributor.SubscriptionSummary.tran.f1
ms.assetid: 1f499277-7f12-42ba-8cf4-52b683434944
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8ca0717a63c9660c225ec238e1e4d2423f7d01ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663387"
---
# <a name="distributor-information-dialog-box"></a><span data-ttu-id="66196-102">Información del distribuidor (cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="66196-102">Distributor Information Dialog Box</span></span> 
<span data-ttu-id="66196-103">En este tema se proporciona información sobre el cuadro de diálogo **distribuidor**</span><span class="sxs-lookup"><span data-stu-id="66196-103">This topic provides information on the **Distributor** dialog box</span></span> 

## <a name="publications"></a><span data-ttu-id="66196-104">Publicaciones</span><span class="sxs-lookup"><span data-stu-id="66196-104">Publications</span></span>

  <span data-ttu-id="66196-105">La pestaña **Publicaciones** proporciona información de resumen para todas las publicaciones del distribuidor seleccionado en el recuadro izquierdo.</span><span class="sxs-lookup"><span data-stu-id="66196-105">The **Publications** tab provides summary information for all publications at the Distributor that is selected in the left pane.</span></span>  
  
### <a name="options"></a><span data-ttu-id="66196-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="66196-106">Options</span></span>  
 <span data-ttu-id="66196-107">La información que se muestra sobre las publicaciones admitidas por el distribuidor incluye una columna que contiene la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del publicador.</span><span class="sxs-lookup"><span data-stu-id="66196-107">The information that is displayed about the publications supported by the Distributor includes a column that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance of the Publisher.</span></span> <span data-ttu-id="66196-108">De lo contrario, la información de publicación será la misma que la información de publicación que se proporciona cuando se ven publicaciones en la vista Publicador del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="66196-108">Otherwise, the publication information is the same as the publication information that is provided when you view publications in the Publisher view of Replication Monitor.</span></span> <span data-ttu-id="66196-109">Para obtener más información sobre las columnas en la pestaña **Publicaciones** , vea [Publisher Information, Publications](publisher-information-publications.md).</span><span class="sxs-lookup"><span data-stu-id="66196-109">For more information about the columns in the **Publications** tab, see [Publisher Information, Publications](publisher-information-publications.md).</span></span>  

## <a name="subscription-watch-list"></a><span data-ttu-id="66196-110">Lista de supervisión de suscripciones</span><span class="sxs-lookup"><span data-stu-id="66196-110">Subscription watch list</span></span>

### <a name="transactional-replication"></a><span data-ttu-id="66196-111">Replicación transaccional</span><span class="sxs-lookup"><span data-stu-id="66196-111">Transactional replication</span></span> 
  <span data-ttu-id="66196-112">La información de las suscripciones transaccionales incluye el nombre del publicador.</span><span class="sxs-lookup"><span data-stu-id="66196-112">Information for transactional subscriptions includes the name of the Publisher.</span></span> <span data-ttu-id="66196-113">De lo contrario, la funcionalidad y la información proporcionadas en este cuadro de diálogo son las mismas que las de la vista Publicador.</span><span class="sxs-lookup"><span data-stu-id="66196-113">Otherwise, the functionality and the information that is provided in this dialog box is the same as in the Publisher view.</span></span> <span data-ttu-id="66196-114">Para más información sobre cómo utilizar este cuadro de diálogo, vea [Publisher Information, Subscription Watch List &#40;Transactional Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-transactional.md) (Información del publicador, Lista de supervisión de suscripciones (Publicación de transacciones, SQL Server 2005 y versiones posteriores)).</span><span class="sxs-lookup"><span data-stu-id="66196-114">For more information about how to use this dialog box, see [Publisher Information, Subscription Watch List &#40;Transactional Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-transactional.md).</span></span>  

### <a name="merge-replication"></a><span data-ttu-id="66196-115">Replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="66196-115">Merge replication</span></span>
  <span data-ttu-id="66196-116">El nombre del publicador se incluye en la información para las suscripciones de publicaciones de combinación.</span><span class="sxs-lookup"><span data-stu-id="66196-116">Information for merge publication subscriptions includes the name of the Publisher.</span></span> <span data-ttu-id="66196-117">De lo contrario, la funcionalidad y la información proporcionadas en este cuadro de diálogo son las mismas que las de la vista Publicador.</span><span class="sxs-lookup"><span data-stu-id="66196-117">Otherwise, the functionality and the information that is provided in this dialog box is the same as in the Publisher view.</span></span> <span data-ttu-id="66196-118">Para más información sobre cómo utilizar este cuadro de diálogo, vea [Publisher Information, Subscription Watch List &#40;Merge Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-merge-publication.md) (Información del publicador, Lista de supervisión de suscripciones (Publicación de mezcla, SQL Server 2005 y versiones posteriores)).</span><span class="sxs-lookup"><span data-stu-id="66196-118">For more information about how to use this dialog box, see [Publisher Information, Subscription Watch List &#40;Merge Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-merge-publication.md).</span></span> 

### <a name="snapshot-replication"></a><span data-ttu-id="66196-119">Replicación de instantáneas</span><span class="sxs-lookup"><span data-stu-id="66196-119">Snapshot replication</span></span>
  <span data-ttu-id="66196-120">El nombre del publicador se incluye en la información para las suscripciones de publicaciones de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="66196-120">Information for snapshot publication subscriptions includes the name of the Publisher.</span></span> <span data-ttu-id="66196-121">De lo contrario, la funcionalidad y la información proporcionadas en este cuadro de diálogo son las mismas que las de la vista Publicador.</span><span class="sxs-lookup"><span data-stu-id="66196-121">Otherwise, the functionality and the information that is provided in this dialog box is the same as in the Publisher view.</span></span> <span data-ttu-id="66196-122">Para más información sobre cómo utilizar este cuadro de diálogo, vea [Publisher Information, Subscription Watch List &#40;Snapshot Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-snapshot.md) (Información del publicador, Lista de supervisión de suscripciones (Publicación de instantáneas, SQL Server 2005 y versiones posteriores)).</span><span class="sxs-lookup"><span data-stu-id="66196-122">For more information about how to use this dialog box, see [Publisher Information, Subscription Watch List &#40;Snapshot Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-snapshot.md).</span></span>  

## <a name="agents"></a><span data-ttu-id="66196-123">Agentes</span><span class="sxs-lookup"><span data-stu-id="66196-123">Agents</span></span>
  <span data-ttu-id="66196-124"> La pestaña **Agentes** muestra información acerca de los agentes y trabajos de mantenimiento asociados con el publicador y el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="66196-124">The **Agents** tab displays information about the agents and maintenance jobs that are associated with the Publisher and Subscriber.</span></span>  
  
 <span data-ttu-id="66196-125">Los agentes que están disponibles en la pestaña **Agentes** de un distribuidor en la vista Distribuidor incluyen todos los agentes que están disponibles en la pestaña **Agentes** de un publicador.</span><span class="sxs-lookup"><span data-stu-id="66196-125">The agents that are available in the **Agents** tab for a Distributor in Distributor view include all the agents that are available in the **Agents** tab for a Publisher.</span></span> <span data-ttu-id="66196-126">Sin embargo, la pestaña **Agentes** para un distribuidor en la vista Distribuidor también incluye un Agente de distribuidor y un Agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="66196-126">However, the **Agents** tab for a Distributor in Distributor view also includes a Distributor Agent and a Merge Agent.</span></span>  
  
 <span data-ttu-id="66196-127">Para obtener más información acerca de los agentes de instantánea, registro del LOB y de lectura de cola, y de los trabajos del mantenimiento, vea [Publisher Information, Agents](publisher-information-agents.md).</span><span class="sxs-lookup"><span data-stu-id="66196-127">For more information about the Snapshot, Log Reader, and Queue Reader agents, and maintenance jobs, see [Publisher Information, Agents](publisher-information-agents.md).</span></span> <span data-ttu-id="66196-128">Observe que cuando está viendo información del agente en la pestaña **Agentes** para un distribuidor, se presenta la información del publicador para los agentes de registro del LOG y de instantánea.</span><span class="sxs-lookup"><span data-stu-id="66196-128">Notice that when you are viewing agent information on the **Agents** tab for a Distributor, Publisher information is present for the Snapshot and Log Reader agents.</span></span> <span data-ttu-id="66196-129">Sin embargo, en la pestaña **Agentes** de un distribuidor de la vista Distribuidor, también puede seleccionar **Agente de distribuidor** y **Agente de mezcla**.</span><span class="sxs-lookup"><span data-stu-id="66196-129">However, in the **Agents** tab for a Distributor in Distributor view, you can also select **Distributor Agent** and **Merge Agent**.</span></span>  
  
### <a name="options"></a><span data-ttu-id="66196-130">Opciones</span><span class="sxs-lookup"><span data-stu-id="66196-130">Options</span></span>  
 <span data-ttu-id="66196-131">En las secciones siguientes se describen los datos que se muestran en esta pestaña para el Agente de distribuidor o Agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="66196-131">The following sections describe the data that is displayed on this tab for the Distributor Agent and Merge Agent.</span></span>  
  
### <a name="distributor-agent"></a><span data-ttu-id="66196-132">Agente de distribuidor</span><span class="sxs-lookup"><span data-stu-id="66196-132">Distributor Agent</span></span>  
 <span data-ttu-id="66196-133">**Estado**</span><span class="sxs-lookup"><span data-stu-id="66196-133">**Status**</span></span>  
 <span data-ttu-id="66196-134">Estado del agente.</span><span class="sxs-lookup"><span data-stu-id="66196-134">The status of the agent.</span></span> <span data-ttu-id="66196-135">En la lista siguiente se muestran los valores de estado posibles:</span><span class="sxs-lookup"><span data-stu-id="66196-135">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="66196-136">Error</span><span class="sxs-lookup"><span data-stu-id="66196-136">Error</span></span>    
-   <span data-ttu-id="66196-137">Volver a intentar</span><span class="sxs-lookup"><span data-stu-id="66196-137">Retry</span></span>    
-   <span data-ttu-id="66196-138">En ejecución</span><span class="sxs-lookup"><span data-stu-id="66196-138">Running</span></span>    
-   <span data-ttu-id="66196-139">No está en ejecución</span><span class="sxs-lookup"><span data-stu-id="66196-139">Not Running</span></span>    
-   <span data-ttu-id="66196-140">No se ha iniciado nunca</span><span class="sxs-lookup"><span data-stu-id="66196-140">Never started</span></span>  
  
 <span data-ttu-id="66196-141">**Publicador**</span><span class="sxs-lookup"><span data-stu-id="66196-141">**Publisher**</span></span>  
 <span data-ttu-id="66196-142">La instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del publicador.</span><span class="sxs-lookup"><span data-stu-id="66196-142">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance of the Publisher.</span></span>  
  
 <span data-ttu-id="66196-143">**Publicación**</span><span class="sxs-lookup"><span data-stu-id="66196-143">**Publication**</span></span>  
 <span data-ttu-id="66196-144">Nombre de la publicación a la que está asociada el agente.</span><span class="sxs-lookup"><span data-stu-id="66196-144">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="66196-145">**Suscripción**</span><span class="sxs-lookup"><span data-stu-id="66196-145">**Subscription**</span></span>  
 <span data-ttu-id="66196-146">Nombre de la suscripción, con el formato: [*SubscriberName*].[*Database*].</span><span class="sxs-lookup"><span data-stu-id="66196-146">The name of the subscription, in the form: [*SubscriberName*].[*Database*].</span></span>  
  
 <span data-ttu-id="66196-147">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="66196-147">**Type**</span></span>  
 <span data-ttu-id="66196-148">Tipo de replicación: inserción, extracción o anónima.</span><span class="sxs-lookup"><span data-stu-id="66196-148">Type of replication: push, pull, or Anonymous.</span></span>  
  
 <span data-ttu-id="66196-149">**Última hora de inicio**</span><span class="sxs-lookup"><span data-stu-id="66196-149">**Last Start Time**</span></span>  
 <span data-ttu-id="66196-150">Última hora en que se inició el agente.</span><span class="sxs-lookup"><span data-stu-id="66196-150">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="66196-151">**Duration**</span><span class="sxs-lookup"><span data-stu-id="66196-151">**Duration**</span></span>  
 <span data-ttu-id="66196-152">Intervalo de tiempo que se ejecutó el agente.</span><span class="sxs-lookup"><span data-stu-id="66196-152">The length of time that the agent has run.</span></span> <span data-ttu-id="66196-153">Este tiempo representa el tiempo transcurrido si el agente se está ejecutando actualmente o el tiempo total de ejecución si ya finalizó la ejecución.</span><span class="sxs-lookup"><span data-stu-id="66196-153">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="66196-154">**Última acción**</span><span class="sxs-lookup"><span data-stu-id="66196-154">**Last Action**</span></span>  
 <span data-ttu-id="66196-155">La última acción realizada durante la ejecución más reciente del agente.</span><span class="sxs-lookup"><span data-stu-id="66196-155">The last action that was performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="66196-156">**Tasa de entrega**</span><span class="sxs-lookup"><span data-stu-id="66196-156">**Delivery Rate**</span></span>  
 <span data-ttu-id="66196-157">La tasa, en comandos por segundo, a la que se confirman los comandos de inicialización en la base de datos de distribución durante la última ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="66196-157">The rate, in commands per second, at which initialization commands are committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="66196-158">**Latency**</span><span class="sxs-lookup"><span data-stu-id="66196-158">**Latency**</span></span>  
 <span data-ttu-id="66196-159">El tiempo, en segundos, que ha transcurrido entre el último cambio confirmado en la base de datos de publicación y el comando correspondiente que se confirma en la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="66196-159">The time, in seconds, that has elapsed between the most recent change being committed in the publication database, and the corresponding command being committed in the distribution database.</span></span>  
  
 <span data-ttu-id="66196-160">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="66196-160">**#Trans**</span></span>  
 <span data-ttu-id="66196-161">El número de transacciones confirmadas en la base de datos de distribución durante la última ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="66196-161">The number of transactions committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="66196-162">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="66196-162">**#Cmds**</span></span>  
 <span data-ttu-id="66196-163">El número de comandos confirmados en la base de datos de distribución durante la última ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="66196-163">The number of commands committed in the distribution database during the most recent run of the agent.</span></span> <span data-ttu-id="66196-164">Un comando es lo mismo que un cambio en los datos, como una actualización.</span><span class="sxs-lookup"><span data-stu-id="66196-164">A command is the same as a data change, such as an update.</span></span>  
  
 <span data-ttu-id="66196-165">**Avg. #Cmds**</span><span class="sxs-lookup"><span data-stu-id="66196-165">**Avg. #Cmds**</span></span>  
 <span data-ttu-id="66196-166">El promedio de comandos por transacción durante la última ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="66196-166">The average number of commands per transaction during the most recent run of the agent.</span></span>  
  
### <a name="merge-agent"></a><span data-ttu-id="66196-167">Agente de mezcla</span><span class="sxs-lookup"><span data-stu-id="66196-167">Merge Agent</span></span>  
 <span data-ttu-id="66196-168">**Estado**</span><span class="sxs-lookup"><span data-stu-id="66196-168">**Status**</span></span>  
 <span data-ttu-id="66196-169">Estado del agente.</span><span class="sxs-lookup"><span data-stu-id="66196-169">The status of the agent.</span></span> <span data-ttu-id="66196-170">En la lista siguiente se muestran los valores de estado posibles:</span><span class="sxs-lookup"><span data-stu-id="66196-170">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="66196-171">Error</span><span class="sxs-lookup"><span data-stu-id="66196-171">Error</span></span>    
-   <span data-ttu-id="66196-172">Volver a intentar</span><span class="sxs-lookup"><span data-stu-id="66196-172">Retry</span></span>    
-   <span data-ttu-id="66196-173">En ejecución</span><span class="sxs-lookup"><span data-stu-id="66196-173">Running</span></span>    
-   <span data-ttu-id="66196-174">No está en ejecución</span><span class="sxs-lookup"><span data-stu-id="66196-174">Not Running</span></span>    
-   <span data-ttu-id="66196-175">No se ha iniciado nunca</span><span class="sxs-lookup"><span data-stu-id="66196-175">Never started</span></span>  
  
 <span data-ttu-id="66196-176">**Publicador**</span><span class="sxs-lookup"><span data-stu-id="66196-176">**Publisher**</span></span>  
 <span data-ttu-id="66196-177">La instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del publicador.</span><span class="sxs-lookup"><span data-stu-id="66196-177">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance of the Publisher.</span></span>  
  
 <span data-ttu-id="66196-178">**Publicación**</span><span class="sxs-lookup"><span data-stu-id="66196-178">**Publication**</span></span>  
 <span data-ttu-id="66196-179">Nombre de la publicación a la que está asociada el agente.</span><span class="sxs-lookup"><span data-stu-id="66196-179">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="66196-180">**Suscripción**</span><span class="sxs-lookup"><span data-stu-id="66196-180">**Subscription**</span></span>  
 <span data-ttu-id="66196-181">Nombre de la suscripción, con el formato: [*SubscriberName*].[*Database*].</span><span class="sxs-lookup"><span data-stu-id="66196-181">The name of the subscription, in the form: [*SubscriberName*].[*Database*].</span></span>  
  
 <span data-ttu-id="66196-182">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="66196-182">**Type**</span></span>  
 <span data-ttu-id="66196-183">Tipo de replicación: inserción, extracción o anónima.</span><span class="sxs-lookup"><span data-stu-id="66196-183">Type of replication: push, pull, or Anonymous.</span></span>  
  
 <span data-ttu-id="66196-184">**Última hora de inicio**</span><span class="sxs-lookup"><span data-stu-id="66196-184">**Last Start Time**</span></span>  
 <span data-ttu-id="66196-185">Última hora en que se inició el agente.</span><span class="sxs-lookup"><span data-stu-id="66196-185">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="66196-186">**Duration**</span><span class="sxs-lookup"><span data-stu-id="66196-186">**Duration**</span></span>  
 <span data-ttu-id="66196-187">Intervalo de tiempo que se ejecutó el agente.</span><span class="sxs-lookup"><span data-stu-id="66196-187">The length of time that the agent has run.</span></span> <span data-ttu-id="66196-188">Este tiempo representa el tiempo transcurrido si el agente se está ejecutando actualmente o el tiempo total de ejecución si ya finalizó la ejecución.</span><span class="sxs-lookup"><span data-stu-id="66196-188">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="66196-189">**Última acción**</span><span class="sxs-lookup"><span data-stu-id="66196-189">**Last Action**</span></span>  
 <span data-ttu-id="66196-190">La última acción realizada durante la ejecución más reciente del agente.</span><span class="sxs-lookup"><span data-stu-id="66196-190">The last action that was performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="66196-191">**Tasa de entrega**</span><span class="sxs-lookup"><span data-stu-id="66196-191">**Delivery Rate**</span></span>  
 <span data-ttu-id="66196-192">La tasa, en comandos por segundo, a la que se confirman los cambios en la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="66196-192">The rate, in commands per second, at which changes are committed in the distribution database.</span></span>  
  
 <span data-ttu-id="66196-193">**Inserciones de publicador**</span><span class="sxs-lookup"><span data-stu-id="66196-193">**Publisher Inserts**</span></span>  
 <span data-ttu-id="66196-194">Número de comandos INSERT aplicados en el publicador.</span><span class="sxs-lookup"><span data-stu-id="66196-194">Number of INSERT commands applied at the Publisher.</span></span>  
  
 <span data-ttu-id="66196-195">**Actualizaciones de publicador**</span><span class="sxs-lookup"><span data-stu-id="66196-195">**Publisher Updates**</span></span>  
 <span data-ttu-id="66196-196">Número de comandos UPDATE aplicados en el publicador.</span><span class="sxs-lookup"><span data-stu-id="66196-196">Number of UPDATE commands applied at the Publisher.</span></span>  
  
 <span data-ttu-id="66196-197">**Eliminaciones de publicador**</span><span class="sxs-lookup"><span data-stu-id="66196-197">**Publisher Deletes**</span></span>  
 <span data-ttu-id="66196-198">Número de comandos DELETE aplicados en el publicador.</span><span class="sxs-lookup"><span data-stu-id="66196-198">Number of DELETE commands applied at the Publisher.</span></span>  
  
 <span data-ttu-id="66196-199">**Conflictos de publicador**</span><span class="sxs-lookup"><span data-stu-id="66196-199">**Publisher Conflicts**</span></span>  
 <span data-ttu-id="66196-200">Número de conflictos producidos en el publicador durante el proceso de mezcla.</span><span class="sxs-lookup"><span data-stu-id="66196-200">The number of conflicts occurring at the Publisher during the merge process.</span></span>  
  
 <span data-ttu-id="66196-201">**Inserciones de suscriptor**</span><span class="sxs-lookup"><span data-stu-id="66196-201">**Subscriber Inserts**</span></span>  
 <span data-ttu-id="66196-202">Número de comandos INSERT aplicados en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="66196-202">Number of INSERT commands applied at the Subscriber.</span></span>  
  
 <span data-ttu-id="66196-203">**Actualizaciones de suscriptor**</span><span class="sxs-lookup"><span data-stu-id="66196-203">**Subscriber Updates**</span></span>  
 <span data-ttu-id="66196-204">Número de comandos UPDATE aplicados en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="66196-204">Number of UPDATE commands applied at the Subscriber.</span></span>  
  
 <span data-ttu-id="66196-205">**Eliminaciones de suscriptor**</span><span class="sxs-lookup"><span data-stu-id="66196-205">**Subscriber Deletes**</span></span>  
 <span data-ttu-id="66196-206">Número de comandos DELETE aplicados en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="66196-206">Number of DELETE commands applied at the Subscriber.</span></span>  
  
 <span data-ttu-id="66196-207">**Conflictos de suscriptor**</span><span class="sxs-lookup"><span data-stu-id="66196-207">**Subscriber Conflicts**</span></span>  
 <span data-ttu-id="66196-208">Número de conflictos producidos en el suscriptor durante el proceso de mezcla.</span><span class="sxs-lookup"><span data-stu-id="66196-208">The number of conflicts occurring at the Subscriber during the merge process.</span></span>  
  
 
## <a name="see-also"></a><span data-ttu-id="66196-209">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66196-209">See Also</span></span>  
 <span data-ttu-id="66196-210">[Iniciar el monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="66196-210">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="66196-211">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="66196-211">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
