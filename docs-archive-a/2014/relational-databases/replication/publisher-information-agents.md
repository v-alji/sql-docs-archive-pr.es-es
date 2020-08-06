---
title: Información de publicador, Agentes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.commonjobs.f1
ms.assetid: 2346c00d-c269-45a1-af14-68e7fd7ebd7e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bdd2055ed022257524bc4d2784bdc333537be855
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662798"
---
# <a name="publisher-information-agents"></a><span data-ttu-id="98da1-102">Información de publicador, Agentes</span><span class="sxs-lookup"><span data-stu-id="98da1-102">Publisher Information, Agents</span></span>
  <span data-ttu-id="98da1-103">La pestaña **Agentes** muestra información sobre los agentes y trabajos de mantenimiento asociados con el publicador:</span><span class="sxs-lookup"><span data-stu-id="98da1-103">The **Agents** tab displays information about the agents and maintenance jobs that are associated with the Publisher:</span></span>  
  
-   <span data-ttu-id="98da1-104">Agente de instantáneas, que se muestra en todas las publicaciones.</span><span class="sxs-lookup"><span data-stu-id="98da1-104">Snapshot Agent, which is displayed for all publications.</span></span>  
  
-   <span data-ttu-id="98da1-105">Agente de registro del LOG, que se muestra en todas las publicaciones transaccionales.</span><span class="sxs-lookup"><span data-stu-id="98da1-105">Log Reader Agent, which is displayed for all transactional publications.</span></span>  
  
-   <span data-ttu-id="98da1-106">Agente de lectura de cola, que se muestra en las publicaciones transaccionales habilitadas para las suscripciones de actualización en cola.</span><span class="sxs-lookup"><span data-stu-id="98da1-106">Queue Reader Agent, which is displayed for those transactional publications that are enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="98da1-107">Trabajos del mantenimiento, que se muestran en todas las publicaciones:</span><span class="sxs-lookup"><span data-stu-id="98da1-107">Maintenance jobs, displayed for all publications:</span></span>  
  
    -   <span data-ttu-id="98da1-108">Reinicialización de suscripciones con errores de validación de datos</span><span class="sxs-lookup"><span data-stu-id="98da1-108">Reinitialize subscriptions that have data validation failures</span></span>  
  
    -   <span data-ttu-id="98da1-109">Limpieza de historial del agente: distribución</span><span class="sxs-lookup"><span data-stu-id="98da1-109">Agent history cleanup: distribution</span></span>  
  
    -   <span data-ttu-id="98da1-110">Actualizador de supervisión de replicación para distribución</span><span class="sxs-lookup"><span data-stu-id="98da1-110">Replication monitoring refresher for distribution</span></span>  
  
    -   <span data-ttu-id="98da1-111">Comprobación de agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="98da1-111">Replication agents checkup</span></span>  
  
    -   <span data-ttu-id="98da1-112">Limpieza de distribución: distribución</span><span class="sxs-lookup"><span data-stu-id="98da1-112">Distribution cleanup: distribution</span></span>  
  
    -   <span data-ttu-id="98da1-113">Limpieza de suscripciones expiradas</span><span class="sxs-lookup"><span data-stu-id="98da1-113">Expired subscription cleanup</span></span>  
  
 <span data-ttu-id="98da1-114">Para obtener más información sobre estos trabajos, vea [Administración del Agente de replicación](agents/replication-agent-administration.md).</span><span class="sxs-lookup"><span data-stu-id="98da1-114">For more information about these jobs, see [Replication Agent Administration](agents/replication-agent-administration.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="98da1-115">Opciones</span><span class="sxs-lookup"><span data-stu-id="98da1-115">Options</span></span>  
 <span data-ttu-id="98da1-116">Para mostrar información sobre un agente o trabajo, seleccione la opción correspondiente en el menú desplegable **Tipos de agente y trabajo** .</span><span class="sxs-lookup"><span data-stu-id="98da1-116">To display information about an agent or job, select from the **Agent and Job Types** drop-down menu.</span></span> <span data-ttu-id="98da1-117">Para obtener información más detallada y ver cuáles son las tareas relacionadas con un agente o un trabajo, haga clic con el botón secundario en la fila del agente o el trabajo correspondiente y después elija una opción del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="98da1-117">For more detailed information and tasks that are related to an agent or job, right-click the row for that agent or job, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="98da1-118">Para cambiar la manera que la cuadrícula muestra los datos, haga clic con el botón secundario en la cuadrícula y, a continuación, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="98da1-118">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="98da1-119">**Ordenar**: ordene en una o más columnas en el cuadro de diálogo **Ordenar columnas** .</span><span class="sxs-lookup"><span data-stu-id="98da1-119">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="98da1-120">**Elegir columnas para mostrar**: seleccione las columnas que se mostrarán y el orden en el que se mostrarán en el cuadro de diálogo **Elegir columnas** .</span><span class="sxs-lookup"><span data-stu-id="98da1-120">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="98da1-121">**Filtro**: filtre filas en la cuadrícula basándose en los valores de columna en el cuadro de diálogo **Configuración del filtro** .</span><span class="sxs-lookup"><span data-stu-id="98da1-121">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="98da1-122">**Borrar filtro**: borre cualquier configuración de filtro para la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="98da1-122">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="98da1-123">La configuración del filtro es específica de cada cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="98da1-123">Filter settings are specific to each grid.</span></span> <span data-ttu-id="98da1-124">La selección y ordenación de las columnas se aplica a todas las cuadrículas del mismo tipo, como la cuadrícula de las publicaciones para cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="98da1-124">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="98da1-125">En las secciones siguientes se describen los datos que se muestran en esta pestaña para cada agente o trabajo.</span><span class="sxs-lookup"><span data-stu-id="98da1-125">The following sections describe the data that is displayed on this tab for each agent or job.</span></span>  
  
### <a name="snapshot-agent"></a><span data-ttu-id="98da1-126">Agente de instantáneas</span><span class="sxs-lookup"><span data-stu-id="98da1-126">Snapshot Agent</span></span>  
 <span data-ttu-id="98da1-127">**Estado**</span><span class="sxs-lookup"><span data-stu-id="98da1-127">**Status**</span></span>  
 <span data-ttu-id="98da1-128">Estado del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-128">The status of the agent.</span></span> <span data-ttu-id="98da1-129">En la lista siguiente se muestran los valores de estado posibles:</span><span class="sxs-lookup"><span data-stu-id="98da1-129">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="98da1-130">Error</span><span class="sxs-lookup"><span data-stu-id="98da1-130">Error</span></span>  
  
-   <span data-ttu-id="98da1-131">Reintento</span><span class="sxs-lookup"><span data-stu-id="98da1-131">Retry</span></span>  
  
-   <span data-ttu-id="98da1-132">En ejecución</span><span class="sxs-lookup"><span data-stu-id="98da1-132">Running</span></span>  
  
-   <span data-ttu-id="98da1-133">Completed</span><span class="sxs-lookup"><span data-stu-id="98da1-133">Completed</span></span>  
  
 <span data-ttu-id="98da1-134">**Publicación**</span><span class="sxs-lookup"><span data-stu-id="98da1-134">**Publication**</span></span>  
 <span data-ttu-id="98da1-135">Nombre de la publicación a la que está asociada el agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-135">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="98da1-136">**Última hora de inicio**</span><span class="sxs-lookup"><span data-stu-id="98da1-136">**Last Start Time**</span></span>  
 <span data-ttu-id="98da1-137">Última hora en que se inició el agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-137">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="98da1-138">**Duration**</span><span class="sxs-lookup"><span data-stu-id="98da1-138">**Duration**</span></span>  
 <span data-ttu-id="98da1-139">Tiempo de ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-139">The length of time the agent has run.</span></span> <span data-ttu-id="98da1-140">Este tiempo representa el tiempo transcurrido si el agente se está ejecutando actualmente o el tiempo total de ejecución si ya finalizó la ejecución.</span><span class="sxs-lookup"><span data-stu-id="98da1-140">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="98da1-141">**Última acción**</span><span class="sxs-lookup"><span data-stu-id="98da1-141">**Last Action**</span></span>  
 <span data-ttu-id="98da1-142">La última acción realizada durante la ejecución más reciente del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-142">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="98da1-143">**Tasa de entrega**</span><span class="sxs-lookup"><span data-stu-id="98da1-143">**Delivery Rate**</span></span>  
 <span data-ttu-id="98da1-144">La tasa, en comandos por segundo, a la que se confirman los comandos de inicialización en la base de datos de distribución durante la última ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-144">The rate, in commands per second, at which initialization commands are committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="98da1-145">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="98da1-145">**#Trans**</span></span>  
 <span data-ttu-id="98da1-146">El número de transacciones confirmadas en la base de datos de distribución durante la última ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-146">The number of transactions committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="98da1-147">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="98da1-147">**#Cmds**</span></span>  
 <span data-ttu-id="98da1-148">El número de comandos confirmados en la base de datos de distribución durante la última ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-148">The number of commands committed in the distribution database during the most recent run of the agent.</span></span> <span data-ttu-id="98da1-149">Un comando equivale a un cambio en los datos, como una actualización.</span><span class="sxs-lookup"><span data-stu-id="98da1-149">A command is equivalent to a data change, such as an update.</span></span>  
  
### <a name="log-reader-agent"></a><span data-ttu-id="98da1-150">Agente de registro del LOG</span><span class="sxs-lookup"><span data-stu-id="98da1-150">Log Reader Agent</span></span>  
 <span data-ttu-id="98da1-151">**Estado**</span><span class="sxs-lookup"><span data-stu-id="98da1-151">**Status**</span></span>  
 <span data-ttu-id="98da1-152">Estado del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-152">The status of the agent.</span></span> <span data-ttu-id="98da1-153">En la lista siguiente se muestran los valores de estado posibles:</span><span class="sxs-lookup"><span data-stu-id="98da1-153">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="98da1-154">Error</span><span class="sxs-lookup"><span data-stu-id="98da1-154">Error</span></span>  
  
-   <span data-ttu-id="98da1-155">Reintento</span><span class="sxs-lookup"><span data-stu-id="98da1-155">Retry</span></span>  
  
-   <span data-ttu-id="98da1-156">En ejecución</span><span class="sxs-lookup"><span data-stu-id="98da1-156">Running</span></span>  
  
-   <span data-ttu-id="98da1-157">No está en ejecución</span><span class="sxs-lookup"><span data-stu-id="98da1-157">Not running</span></span>  
  
 <span data-ttu-id="98da1-158">**Base de datos de publicaciones**</span><span class="sxs-lookup"><span data-stu-id="98da1-158">**Publication Database**</span></span>  
 <span data-ttu-id="98da1-159">Nombre de la publicación a la que está asociada el agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-159">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="98da1-160">**Última hora de inicio**</span><span class="sxs-lookup"><span data-stu-id="98da1-160">**Last Start Time**</span></span>  
 <span data-ttu-id="98da1-161">Última hora en que se inició el agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-161">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="98da1-162">**Duration**</span><span class="sxs-lookup"><span data-stu-id="98da1-162">**Duration**</span></span>  
 <span data-ttu-id="98da1-163">Tiempo de ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-163">The length of time the agent has run.</span></span> <span data-ttu-id="98da1-164">Este tiempo representa el tiempo transcurrido si el agente se está ejecutando actualmente o el tiempo total de ejecución si ya finalizó la ejecución.</span><span class="sxs-lookup"><span data-stu-id="98da1-164">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="98da1-165">**Última acción**</span><span class="sxs-lookup"><span data-stu-id="98da1-165">**Last Action**</span></span>  
 <span data-ttu-id="98da1-166">La última acción realizada durante la ejecución más reciente del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-166">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="98da1-167">**Tasa de entrega**</span><span class="sxs-lookup"><span data-stu-id="98da1-167">**Delivery Rate**</span></span>  
 <span data-ttu-id="98da1-168">La tasa, en comandos por segundo, a la que se confirman los cambios en la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="98da1-168">The rate, in commands per second, at which changes are committed in the distribution database.</span></span>  
  
 <span data-ttu-id="98da1-169">**Latency**</span><span class="sxs-lookup"><span data-stu-id="98da1-169">**Latency**</span></span>  
 <span data-ttu-id="98da1-170">El tiempo, en segundos, que ha transcurrido entre el último cambio confirmado en la base de datos de publicación y el comando correspondiente que se confirma en la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="98da1-170">The amount of time, in seconds, that has elapsed between the most recent change being committed in the publication database, and the corresponding command being committed in the distribution database.</span></span>  
  
 <span data-ttu-id="98da1-171">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="98da1-171">**#Trans**</span></span>  
 <span data-ttu-id="98da1-172">El número de transacciones confirmadas en la base de datos de distribución durante la última ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-172">The number of transactions committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="98da1-173">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="98da1-173">**#Cmds**</span></span>  
 <span data-ttu-id="98da1-174">El número de comandos confirmados en la base de datos de distribución durante la última ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-174">The number of commands committed in the distribution database during the most recent run of the agent.</span></span> <span data-ttu-id="98da1-175">Un comando equivale a un cambio en los datos, como una actualización.</span><span class="sxs-lookup"><span data-stu-id="98da1-175">A command is equivalent to a data change, such as an update.</span></span>  
  
 <span data-ttu-id="98da1-176">**Avg. #Cmds**</span><span class="sxs-lookup"><span data-stu-id="98da1-176">**Avg. #Cmds**</span></span>  
 <span data-ttu-id="98da1-177">El promedio de comandos por transacción durante la última ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-177">The average number of commands per transaction during the most recent run of the agent.</span></span>  
  
### <a name="queue-reader-agent"></a><span data-ttu-id="98da1-178">Agente de lectura de cola</span><span class="sxs-lookup"><span data-stu-id="98da1-178">Queue Reader Agent</span></span>  
 <span data-ttu-id="98da1-179">**Estado**</span><span class="sxs-lookup"><span data-stu-id="98da1-179">**Status**</span></span>  
 <span data-ttu-id="98da1-180">Estado del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-180">The status of the agent.</span></span> <span data-ttu-id="98da1-181">En la lista siguiente se muestran los valores de estado posibles:</span><span class="sxs-lookup"><span data-stu-id="98da1-181">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="98da1-182">Error</span><span class="sxs-lookup"><span data-stu-id="98da1-182">Error</span></span>  
  
-   <span data-ttu-id="98da1-183">Reintento</span><span class="sxs-lookup"><span data-stu-id="98da1-183">Retry</span></span>  
  
-   <span data-ttu-id="98da1-184">En ejecución</span><span class="sxs-lookup"><span data-stu-id="98da1-184">Running</span></span>  
  
-   <span data-ttu-id="98da1-185">No está en ejecución</span><span class="sxs-lookup"><span data-stu-id="98da1-185">Not running</span></span>  
  
 <span data-ttu-id="98da1-186">**Base de datos de distribución**</span><span class="sxs-lookup"><span data-stu-id="98da1-186">**Distribution Database**</span></span>  
 <span data-ttu-id="98da1-187">Nombre de la base de datos de distribución a la que está asociada el agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-187">The name of the distribution database with which the agent is associated.</span></span>  
  
 <span data-ttu-id="98da1-188">**Última hora de inicio**</span><span class="sxs-lookup"><span data-stu-id="98da1-188">**Last Start Time**</span></span>  
 <span data-ttu-id="98da1-189">Última hora en que se inició el agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-189">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="98da1-190">**Duration**</span><span class="sxs-lookup"><span data-stu-id="98da1-190">**Duration**</span></span>  
 <span data-ttu-id="98da1-191">Tiempo de ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-191">The length of time the agent has run.</span></span> <span data-ttu-id="98da1-192">Este tiempo representa el tiempo transcurrido si el agente se está ejecutando actualmente o el tiempo total de ejecución si ya finalizó la ejecución.</span><span class="sxs-lookup"><span data-stu-id="98da1-192">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="98da1-193">**Última acción**</span><span class="sxs-lookup"><span data-stu-id="98da1-193">**Last Action**</span></span>  
 <span data-ttu-id="98da1-194">La última acción realizada durante la ejecución más reciente del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-194">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="98da1-195">**Tasa de entrega**</span><span class="sxs-lookup"><span data-stu-id="98da1-195">**Delivery Rate**</span></span>  
 <span data-ttu-id="98da1-196">La tasa, en comandos por segundo, a la que se confirman los cambios en la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="98da1-196">The rate, in commands per second, at which changes are committed in the distribution database.</span></span>  
  
 <span data-ttu-id="98da1-197">**Latency**</span><span class="sxs-lookup"><span data-stu-id="98da1-197">**Latency**</span></span>  
 <span data-ttu-id="98da1-198">El tiempo, en segundos, que ha transcurrido entre el último cambio confirmado en una base de datos de suscripciones y el comando correspondiente que se confirma en la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="98da1-198">The amount of time, in seconds, that has elapsed between the most recent change being committed in a subscription database, and the corresponding command being committed in the publication database.</span></span>  
  
 <span data-ttu-id="98da1-199">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="98da1-199">**#Trans**</span></span>  
 <span data-ttu-id="98da1-200">El número de transacciones confirmadas en la base de datos de publicación durante la última ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-200">The number of transactions committed in the publication database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="98da1-201">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="98da1-201">**#Cmds**</span></span>  
 <span data-ttu-id="98da1-202">El número de comandos confirmados en la base de datos de publicación durante la última ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-202">The number of commands committed in the publication database during the most recent run of the agent.</span></span> <span data-ttu-id="98da1-203">Un comando equivale a un cambio en los datos, como una actualización.</span><span class="sxs-lookup"><span data-stu-id="98da1-203">A command is equivalent to a data change, such as an update.</span></span>  
  
 <span data-ttu-id="98da1-204">**Avg. #Cmds**</span><span class="sxs-lookup"><span data-stu-id="98da1-204">**Avg. #Cmds**</span></span>  
 <span data-ttu-id="98da1-205">El promedio de comandos por transacción durante la última ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="98da1-205">The average number of commands per transaction during the most recent run of the agent.</span></span>  
  
### <a name="maintenance-jobs"></a><span data-ttu-id="98da1-206">Trabajos de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="98da1-206">Maintenance Jobs</span></span>  
 <span data-ttu-id="98da1-207">**Estado**</span><span class="sxs-lookup"><span data-stu-id="98da1-207">**Status**</span></span>  
 <span data-ttu-id="98da1-208">Indica el estado de cada trabajo.</span><span class="sxs-lookup"><span data-stu-id="98da1-208">The status of each job.</span></span> <span data-ttu-id="98da1-209">En la lista siguiente se muestran los valores de estado posibles:</span><span class="sxs-lookup"><span data-stu-id="98da1-209">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="98da1-210">Error</span><span class="sxs-lookup"><span data-stu-id="98da1-210">Error</span></span>  
  
-   <span data-ttu-id="98da1-211">Reintento</span><span class="sxs-lookup"><span data-stu-id="98da1-211">Retry</span></span>  
  
-   <span data-ttu-id="98da1-212">En ejecución</span><span class="sxs-lookup"><span data-stu-id="98da1-212">Running</span></span>  
  
-   <span data-ttu-id="98da1-213">No está en ejecución</span><span class="sxs-lookup"><span data-stu-id="98da1-213">Not running</span></span>  
  
 <span data-ttu-id="98da1-214">**Trabajo**</span><span class="sxs-lookup"><span data-stu-id="98da1-214">**Job**</span></span>  
 <span data-ttu-id="98da1-215">Nombre del trabajo.</span><span class="sxs-lookup"><span data-stu-id="98da1-215">The name of the job.</span></span>  
  
 <span data-ttu-id="98da1-216">**Última hora de inicio**</span><span class="sxs-lookup"><span data-stu-id="98da1-216">**Last Start Time**</span></span>  
 <span data-ttu-id="98da1-217">Última hora en que se inició el trabajo.</span><span class="sxs-lookup"><span data-stu-id="98da1-217">The last time at which the job started.</span></span>  
  
 <span data-ttu-id="98da1-218">**Duration**</span><span class="sxs-lookup"><span data-stu-id="98da1-218">**Duration**</span></span>  
 <span data-ttu-id="98da1-219">Tiempo durante el que se ha ejecutado el trabajo.</span><span class="sxs-lookup"><span data-stu-id="98da1-219">The length of time the job has run.</span></span> <span data-ttu-id="98da1-220">El tiempo representa el tiempo transcurrido si el trabajo se está ejecutando y el tiempo total si el trabajo se ha ejecutado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="98da1-220">The time represents elapsed time if the job is currently running, and total time if the job has run previously.</span></span>  
  
 <span data-ttu-id="98da1-221">**Última acción**</span><span class="sxs-lookup"><span data-stu-id="98da1-221">**Last Action**</span></span>  
 <span data-ttu-id="98da1-222">La última acción realizada durante la ejecución más reciente del trabajo.</span><span class="sxs-lookup"><span data-stu-id="98da1-222">The last action performed during the most recent run of the job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98da1-223">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98da1-223">See Also</span></span>  
 <span data-ttu-id="98da1-224">[Iniciar el Monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="98da1-224">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="98da1-225">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="98da1-225">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="98da1-226">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="98da1-226">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
