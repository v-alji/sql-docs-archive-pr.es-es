---
title: Suscripción, historial de sincronizaciones (suscripción de mezcla, SQL Server 2005 y versiones posteriores) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.synchhistory.f1
- sql12.rep.monitor.subscription.downlevelsynchhistory.f1
ms.assetid: 85f666f6-14ee-4f19-b385-e5cc508aabe4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 49fe19f22976116813ac2454b2d08fc1fe47d8de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675808"
---
# <a name="subscription-synchronization-history-merge-subscription-sql-server-2005-and-later"></a><span data-ttu-id="9dd61-102">Suscripción, Historial de sincronizaciones (suscripción de mezcla, SQL Server 2005 y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="9dd61-102">Subscription, Synchronization History (Merge Subscription, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="9dd61-103">La pestaña **Historial de sincronizaciones** muestra información detallada sobre el Agente de mezcla, incluido el estado, las estadísticas de artículos, el historial, mensajes de información y mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="9dd61-103">The **Synchronization History** tab displays detailed information on the Merge Agent, including status, article statistics, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9dd61-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="9dd61-104">Options</span></span>  
 <span data-ttu-id="9dd61-105">Seleccione en el menú **Ver** las sesiones del Agente de mezcla que desea ver y después seleccione una sesión específica en la cuadrícula con la etiqueta **Sesiones del Agente de mezcla**.</span><span class="sxs-lookup"><span data-stu-id="9dd61-105">Select which Merge Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Merge Agent**.</span></span> <span data-ttu-id="9dd61-106">En la cuadrícula con la etiqueta **Artículos procesados en la sesión seleccionada**se muestra información detallada sobre la sesión.</span><span class="sxs-lookup"><span data-stu-id="9dd61-106">Detailed information on this session is displayed in the grid labeled **Articles processed in the selected session**.</span></span>  
  
 <span data-ttu-id="9dd61-107">**Vista**</span><span class="sxs-lookup"><span data-stu-id="9dd61-107">**View**</span></span>  
 <span data-ttu-id="9dd61-108">Permite seleccionar las sesiones del Agente de mezcla que desea ver.</span><span class="sxs-lookup"><span data-stu-id="9dd61-108">Select which Merge Agent sessions to view.</span></span>  
  
 <span data-ttu-id="9dd61-109">**Estado**</span><span class="sxs-lookup"><span data-stu-id="9dd61-109">**Status**</span></span>  
 <span data-ttu-id="9dd61-110">Estado del Agente de mezcla al final de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9dd61-110">The status of the Merge Agent at the end of the session.</span></span> <span data-ttu-id="9dd61-111">En la lista siguiente se muestran los valores de estado posibles:</span><span class="sxs-lookup"><span data-stu-id="9dd61-111">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="9dd61-112">Error</span><span class="sxs-lookup"><span data-stu-id="9dd61-112">Error</span></span>  
  
-   <span data-ttu-id="9dd61-113">Completed</span><span class="sxs-lookup"><span data-stu-id="9dd61-113">Completed</span></span>  
  
-   <span data-ttu-id="9dd61-114">Intentando de nuevo</span><span class="sxs-lookup"><span data-stu-id="9dd61-114">Retrying</span></span>  
  
-   <span data-ttu-id="9dd61-115">En ejecución</span><span class="sxs-lookup"><span data-stu-id="9dd61-115">Running</span></span>  
  
 <span data-ttu-id="9dd61-116">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="9dd61-116">**Start Time**</span></span>  
 <span data-ttu-id="9dd61-117">Muestra la hora de inicio de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9dd61-117">The start time of the session.</span></span>  
  
 <span data-ttu-id="9dd61-118">**Hora de finalización**</span><span class="sxs-lookup"><span data-stu-id="9dd61-118">**End Time**</span></span>  
 <span data-ttu-id="9dd61-119">Muestra la hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9dd61-119">The end time of the session.</span></span> <span data-ttu-id="9dd61-120">Si no se ha detenido el agente, el campo se mostrará vacío.</span><span class="sxs-lookup"><span data-stu-id="9dd61-120">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="9dd61-121">**Duration**</span><span class="sxs-lookup"><span data-stu-id="9dd61-121">**Duration**</span></span>  
 <span data-ttu-id="9dd61-122">Tiempo de ejecución del Agente de mezcla en una sesión.</span><span class="sxs-lookup"><span data-stu-id="9dd61-122">The amount of time the Merge Agent has run in a session.</span></span> <span data-ttu-id="9dd61-123">Este tiempo representa el tiempo transcurrido si el agente se está ejecutando actualmente o el tiempo total de ejecución si ya finalizó la ejecución.</span><span class="sxs-lookup"><span data-stu-id="9dd61-123">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="9dd61-124">**Comandos cargados**</span><span class="sxs-lookup"><span data-stu-id="9dd61-124">**Uploaded Commands**</span></span>  
 <span data-ttu-id="9dd61-125">Número de filas cargadas durante la sesión del Agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="9dd61-125">The number of rows uploaded during the Merge Agent session.</span></span>  
  
 <span data-ttu-id="9dd61-126">**Comandos descargados**</span><span class="sxs-lookup"><span data-stu-id="9dd61-126">**Downloaded Commands**</span></span>  
 <span data-ttu-id="9dd61-127">Número de filas descargadas durante la sesión del Agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="9dd61-127">The number of rows downloaded during the Merge Agent session.</span></span>  
  
 <span data-ttu-id="9dd61-128">**Mensaje de error**</span><span class="sxs-lookup"><span data-stu-id="9dd61-128">**Error Message**</span></span>  
 <span data-ttu-id="9dd61-129">Si la sesión finalizó con un error, este campo muestra el último mensaje de error registrado por el Agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="9dd61-129">If a session ended in an error, this field displays the last error message logged by the Merge Agent.</span></span> <span data-ttu-id="9dd61-130">Si la sesión no ha finalizado con error, el campo se mostrará vacío.</span><span class="sxs-lookup"><span data-stu-id="9dd61-130">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="9dd61-131">**Artículo**</span><span class="sxs-lookup"><span data-stu-id="9dd61-131">**Article**</span></span>  
 <span data-ttu-id="9dd61-132">Nombre de cada artículo de la publicación y las siguientes fases de procesamiento para la publicación completa:</span><span class="sxs-lookup"><span data-stu-id="9dd61-132">The name of each article in the publication, and the following processing phases for the entire publication:</span></span>  
  
-   <span data-ttu-id="9dd61-133">**Inicialización**.</span><span class="sxs-lookup"><span data-stu-id="9dd61-133">**Initialization**.</span></span> <span data-ttu-id="9dd61-134">Se refiere a iniciar el Agente de mezcla (no es sinónimo de inicializar una suscripción, que implica aplicar una instantánea).</span><span class="sxs-lookup"><span data-stu-id="9dd61-134">This refers to starting the Merge Agent; this is not synonymous with initializing a subscription, which involves applying a snapshot.</span></span>  
  
-   <span data-ttu-id="9dd61-135">**Cambios de esquema e inserciones masivas**.</span><span class="sxs-lookup"><span data-stu-id="9dd61-135">**Schema changes and bulk inserts**.</span></span>  
  
-   <span data-ttu-id="9dd61-136">**Cargar cambios al publicador**.</span><span class="sxs-lookup"><span data-stu-id="9dd61-136">**Upload changes to Publisher**.</span></span>  
  
-   <span data-ttu-id="9dd61-137">**Descargar cambios al suscriptor**.</span><span class="sxs-lookup"><span data-stu-id="9dd61-137">**Download changes to Subscriber**.</span></span>  
  
 <span data-ttu-id="9dd61-138">Se incluyen las fases para que la cuadrícula pueda mostrar la cantidad de tiempo y el porcentaje del tiempo total dedicado a cada fase en la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9dd61-138">The phases are included so that the grid can display the amount of time and percentage of total time that each phase accounts for in the selected session.</span></span>  
  
 <span data-ttu-id="9dd61-139">**% del total**</span><span class="sxs-lookup"><span data-stu-id="9dd61-139">**% of total**</span></span>  
 <span data-ttu-id="9dd61-140">Porcentaje del tiempo total de procesamiento dedicado a cada fase en la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9dd61-140">The percentage of total processing time that each phase accounts for in the selected session.</span></span>  
  
 <span data-ttu-id="9dd61-141">**Duration**</span><span class="sxs-lookup"><span data-stu-id="9dd61-141">**Duration**</span></span>  
 <span data-ttu-id="9dd61-142">Tiempo dedicado a cada fase de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="9dd61-142">The amount of time spent in each processing phase.</span></span> <span data-ttu-id="9dd61-143">Este tiempo representa el tiempo transcurrido si el Agente de mezcla se está ejecutando actualmente para la sesión y el tiempo total de ejecución si ya finalizó su ejecución.</span><span class="sxs-lookup"><span data-stu-id="9dd61-143">The time represents elapsed time if the Merge Agent is currently running for the session and total time if the Merge Agent has run previously.</span></span>  
  
 <span data-ttu-id="9dd61-144">**Inserts**</span><span class="sxs-lookup"><span data-stu-id="9dd61-144">**Inserts**</span></span>  
 <span data-ttu-id="9dd61-145">Número de filas insertadas en esta fase de la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9dd61-145">The number of rows inserted in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="9dd61-146">**Actualizaciones**</span><span class="sxs-lookup"><span data-stu-id="9dd61-146">**Updates**</span></span>  
 <span data-ttu-id="9dd61-147">Número de filas actualizadas en esta fase de la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9dd61-147">The number of rows updated in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="9dd61-148">**Eliminaciones**</span><span class="sxs-lookup"><span data-stu-id="9dd61-148">**Deletes**</span></span>  
 <span data-ttu-id="9dd61-149">Número de filas eliminadas en esta fase de la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9dd61-149">The number of rows deleted in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="9dd61-150">**Conflictos**</span><span class="sxs-lookup"><span data-stu-id="9dd61-150">**Conflicts**</span></span>  
 <span data-ttu-id="9dd61-151">Número de conflictos en la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9dd61-151">The number of conflicts in the selected session.</span></span>  
  
 <span data-ttu-id="9dd61-152">**Cambios de esquema**</span><span class="sxs-lookup"><span data-stu-id="9dd61-152">**Schema Changes**</span></span>  
 <span data-ttu-id="9dd61-153">Número de cambios de esquema en la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9dd61-153">The number of schema changes in the selected session.</span></span> <span data-ttu-id="9dd61-154">Los cambios de esquema pueden ser resultado de: cambios de esquema replicados desde la base de datos de publicación, adición o eliminación de artículos, o cambios de propiedades de un artículo o una publicación.</span><span class="sxs-lookup"><span data-stu-id="9dd61-154">Schema changes can result from: schema changes being replicated from the publication database; adding or dropping articles; and changes to article or publication properties.</span></span>  
  
 <span data-ttu-id="9dd61-155">**Último mensaje de la sesión seleccionada**</span><span class="sxs-lookup"><span data-stu-id="9dd61-155">**Last message of the selected session**</span></span>  
 <span data-ttu-id="9dd61-156">Esta área de texto muestra el último mensaje de la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9dd61-156">This text area displays the last message in the selected session.</span></span> <span data-ttu-id="9dd61-157">Cuando se produce un error se muestra información detallada sobre el error y el comando que se estaba ejecutando.</span><span class="sxs-lookup"><span data-stu-id="9dd61-157">If an error has occurred, it displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="9dd61-158">También incluye vínculos a la información adicional relativa al error.</span><span class="sxs-lookup"><span data-stu-id="9dd61-158">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dd61-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9dd61-159">See Also</span></span>  
 <span data-ttu-id="9dd61-160">[Iniciar el Monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="9dd61-160">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="9dd61-161">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="9dd61-161">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="9dd61-162">[Monitoring Replication](monitoring-replication.md)  (Supervisar la replicación)</span><span class="sxs-lookup"><span data-stu-id="9dd61-162">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="9dd61-163">Información general sobre los agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="9dd61-163">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
