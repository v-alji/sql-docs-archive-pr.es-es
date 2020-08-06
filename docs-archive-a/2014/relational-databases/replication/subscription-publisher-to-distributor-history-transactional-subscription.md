---
title: Suscripción, Historial de Publicador a distribuidor (suscripción transaccional) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.pubtodist.tran.f1
ms.assetid: d5a4c697-1342-49fd-8b7b-b059af32556a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3806c59e545e325fa7e60f2cd92a4b990b0505cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752102"
---
# <a name="subscription-publisher-to-distributor-history-transactional-subscription"></a><span data-ttu-id="de03e-102">Suscripción, Historial de Publicador a distribuidor (suscripción transaccional)</span><span class="sxs-lookup"><span data-stu-id="de03e-102">Subscription, Publisher to Distributor History (Transactional Subscription)</span></span>
  <span data-ttu-id="de03e-103">La pestaña **Historial de Publicador a distribuidor** muestra información detallada en el Agente de registro del LOG, incluidos el estado, el historial y los mensajes informativos, así como cualquier mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="de03e-103">The **Publisher to Distributor History** tab displays detailed information on the Log Reader Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="de03e-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="de03e-104">Options</span></span>  
 <span data-ttu-id="de03e-105">Seleccione las sesiones del Agente de registro del LOG que se van a ver en el menú **Ver** y, a continuación, seleccione una sesión específica en la cuadrícula con la etiqueta **Sesiones del Agente de registro del LOG**.</span><span class="sxs-lookup"><span data-stu-id="de03e-105">Select which Log Reader Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Log Reader Agent**.</span></span> <span data-ttu-id="de03e-106">En la cuadrícula con la etiqueta **Acciones en la sesión seleccionada**se muestra información detallada de la sesión.</span><span class="sxs-lookup"><span data-stu-id="de03e-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="de03e-107">Si la sesión seleccionada finalizó con un error, también se muestra el área de texto con la etiqueta **Detalles del error o mensaje de la sesión seleccionada** .</span><span class="sxs-lookup"><span data-stu-id="de03e-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="de03e-108">**Ver**</span><span class="sxs-lookup"><span data-stu-id="de03e-108">**View**</span></span>  
 <span data-ttu-id="de03e-109">Seleccione las sesiones del Agente de registro del LOG que se van a ver.</span><span class="sxs-lookup"><span data-stu-id="de03e-109">Select which Log Reader Agent sessions to view.</span></span> <span data-ttu-id="de03e-110">Normalmente, el Agente de registro del LOG se ejecuta sin interrupción, por lo que es posible que solo haya una sesión para ver.</span><span class="sxs-lookup"><span data-stu-id="de03e-110">The Log Reader Agent typically runs continuously, therefore there might be only one session to view.</span></span>  
  
 <span data-ttu-id="de03e-111">**Estado**</span><span class="sxs-lookup"><span data-stu-id="de03e-111">**Status**</span></span>  
 <span data-ttu-id="de03e-112">Indica el estado del Agente de registro del LOG.</span><span class="sxs-lookup"><span data-stu-id="de03e-112">The status of the Log Reader Agent.</span></span> <span data-ttu-id="de03e-113">En la lista siguiente se muestran los valores de estado posibles:</span><span class="sxs-lookup"><span data-stu-id="de03e-113">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="de03e-114">Error</span><span class="sxs-lookup"><span data-stu-id="de03e-114">Error</span></span>  
  
-   <span data-ttu-id="de03e-115">Completed</span><span class="sxs-lookup"><span data-stu-id="de03e-115">Completed</span></span>  
  
-   <span data-ttu-id="de03e-116">Intentando de nuevo</span><span class="sxs-lookup"><span data-stu-id="de03e-116">Retrying</span></span>  
  
-   <span data-ttu-id="de03e-117">En ejecución</span><span class="sxs-lookup"><span data-stu-id="de03e-117">Running</span></span>  
  
 <span data-ttu-id="de03e-118">**Hora de inicio**</span><span class="sxs-lookup"><span data-stu-id="de03e-118">**Start Time**</span></span>  
 <span data-ttu-id="de03e-119">Muestra la hora de inicio de la sesión.</span><span class="sxs-lookup"><span data-stu-id="de03e-119">The start time of the session.</span></span>  
  
 <span data-ttu-id="de03e-120">**Hora de finalización**</span><span class="sxs-lookup"><span data-stu-id="de03e-120">**End Time**</span></span>  
 <span data-ttu-id="de03e-121">Muestra la hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="de03e-121">The end time of the session.</span></span> <span data-ttu-id="de03e-122">Si no se ha detenido el agente, el campo se mostrará vacío.</span><span class="sxs-lookup"><span data-stu-id="de03e-122">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="de03e-123">**Duration**</span><span class="sxs-lookup"><span data-stu-id="de03e-123">**Duration**</span></span>  
 <span data-ttu-id="de03e-124">Período de tiempo durante el que se ha ejecutado el Agente de registro del LOG en esta sesión.</span><span class="sxs-lookup"><span data-stu-id="de03e-124">The amount of time the Log Reader Agent has run in this session.</span></span> <span data-ttu-id="de03e-125">El tiempo representa el tiempo transcurrido si el agente se está ejecutando, y el tiempo total de la sesión si la sesión del agente ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="de03e-125">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="de03e-126">**Mensaje de error**</span><span class="sxs-lookup"><span data-stu-id="de03e-126">**Error Message**</span></span>  
 <span data-ttu-id="de03e-127">Si una sesión ha finalizado con un error, este campo muestra el último mensaje de error registrado por el Agente de registro del LOG.</span><span class="sxs-lookup"><span data-stu-id="de03e-127">If a session ended in an error, this field displays the last error message logged by the Log Reader Agent.</span></span> <span data-ttu-id="de03e-128">Si la sesión no ha finalizado con error, el campo se mostrará vacío.</span><span class="sxs-lookup"><span data-stu-id="de03e-128">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="de03e-129">**Mensaje de la acción**</span><span class="sxs-lookup"><span data-stu-id="de03e-129">**Action Message**</span></span>  
 <span data-ttu-id="de03e-130">Muestra todos los mensajes informativos y los mensajes de error que ha registrado el Agente de registro del LOG durante la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="de03e-130">All informational messages and error messages that the Log Reader Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="de03e-131">**Hora de la acción**</span><span class="sxs-lookup"><span data-stu-id="de03e-131">**Action Time**</span></span>  
 <span data-ttu-id="de03e-132">Muestra la hora de realización de la acción descrita en la columna **Mensaje de la acción** .</span><span class="sxs-lookup"><span data-stu-id="de03e-132">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="de03e-133">**Detalles del error o mensaje de la sesión seleccionada**</span><span class="sxs-lookup"><span data-stu-id="de03e-133">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="de03e-134">Solo se muestra si la sesión seleccionada presenta un valor de **Error** en la columna **Estado** .</span><span class="sxs-lookup"><span data-stu-id="de03e-134">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="de03e-135">El área de texto muestra la información detallada del error y el comando que se intentaba ejecutar en el momento de producirse el error.</span><span class="sxs-lookup"><span data-stu-id="de03e-135">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="de03e-136">También incluye vínculos a la información adicional relativa al error.</span><span class="sxs-lookup"><span data-stu-id="de03e-136">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de03e-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de03e-137">See Also</span></span>  
 <span data-ttu-id="de03e-138">[Iniciar el monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="de03e-138">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="de03e-139">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="de03e-139">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="de03e-140">[Monitoring Replication](monitoring-replication.md)  (Supervisar la replicación)</span><span class="sxs-lookup"><span data-stu-id="de03e-140">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="de03e-141">Información general sobre los agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="de03e-141">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
