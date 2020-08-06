---
title: Agente de lectura de cola | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.queuereaderagent.f1
helpviewer_keywords:
- Queue Reader Agent dialog box
ms.assetid: f02d24b6-dcb5-4126-b56e-fab41cfe4337
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9649223b35562da97744d79f9506615b97274870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676470"
---
# <a name="queue-reader-agent"></a><span data-ttu-id="7e069-102">Agente de lectura de cola</span><span class="sxs-lookup"><span data-stu-id="7e069-102">Queue Reader Agent</span></span>
  <span data-ttu-id="7e069-103">El cuadro de diálogo **Agente de lectura de cola** muestra información detallada sobre el Agente de lectura de cola, incluyendo mensajes de estado, históricos e informativos, así como mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="7e069-103">The **Queue Reader Agent** dialog box displays detailed information on the Queue Reader Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7e069-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="7e069-104">Options</span></span>  
 <span data-ttu-id="7e069-105">Seleccione las sesiones del Agente de lectura de cola que deben mostrarse en el menú **Ver** y, a continuación, seleccione una sesión específica en la cuadrícula **Sesiones del Agente de lectura de cola**.</span><span class="sxs-lookup"><span data-stu-id="7e069-105">Select which Queue Reader Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Queue Reader Agent**.</span></span> <span data-ttu-id="7e069-106">En la cuadrícula con la etiqueta **Acciones en la sesión seleccionada**se muestra información detallada de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e069-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="7e069-107">Si la sesión seleccionada finalizó con un error, también se muestra el área de texto con la etiqueta **Detalles del error o mensaje de la sesión seleccionada** .</span><span class="sxs-lookup"><span data-stu-id="7e069-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="7e069-108">**Vista**</span><span class="sxs-lookup"><span data-stu-id="7e069-108">**View**</span></span>  
 <span data-ttu-id="7e069-109">Seleccione las sesiones del Agente de lectura de cola que deben mostrarse.</span><span class="sxs-lookup"><span data-stu-id="7e069-109">Select which Queue Reader Agent sessions to view.</span></span> <span data-ttu-id="7e069-110">Generalmente, el Agente de lectura de cola se ejecuta de forma continuada, por lo que es posible que solo haya una sesión para mostrar.</span><span class="sxs-lookup"><span data-stu-id="7e069-110">The Queue Reader Agent typically runs continuously, therefore there might be only one session to view.</span></span>  
  
 <span data-ttu-id="7e069-111">**Estado**</span><span class="sxs-lookup"><span data-stu-id="7e069-111">**Status**</span></span>  
 <span data-ttu-id="7e069-112">Estado del Agente de lectura de cola.</span><span class="sxs-lookup"><span data-stu-id="7e069-112">The status of the Queue Reader Agent.</span></span> <span data-ttu-id="7e069-113">En la lista siguiente se muestran los valores de estado posibles:</span><span class="sxs-lookup"><span data-stu-id="7e069-113">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="7e069-114">Error</span><span class="sxs-lookup"><span data-stu-id="7e069-114">Error</span></span>  
  
-   <span data-ttu-id="7e069-115">Reintentando comandos con errores</span><span class="sxs-lookup"><span data-stu-id="7e069-115">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="7e069-116">No está en ejecución</span><span class="sxs-lookup"><span data-stu-id="7e069-116">Not running</span></span>  
  
-   <span data-ttu-id="7e069-117">En ejecución</span><span class="sxs-lookup"><span data-stu-id="7e069-117">Running</span></span>  
  
 <span data-ttu-id="7e069-118">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="7e069-118">**Start Time**</span></span>  
 <span data-ttu-id="7e069-119">Muestra la hora de inicio de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e069-119">The start time of the session.</span></span>  
  
 <span data-ttu-id="7e069-120">**Hora de finalización**</span><span class="sxs-lookup"><span data-stu-id="7e069-120">**End Time**</span></span>  
 <span data-ttu-id="7e069-121">Muestra la hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e069-121">The end time of the session.</span></span> <span data-ttu-id="7e069-122">Si no se ha detenido el agente, el campo se mostrará vacío.</span><span class="sxs-lookup"><span data-stu-id="7e069-122">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="7e069-123">**Duration**</span><span class="sxs-lookup"><span data-stu-id="7e069-123">**Duration**</span></span>  
 <span data-ttu-id="7e069-124">Período de tiempo durante el que el Agente de lectura de cola se ha ejecutado en esta sesión.</span><span class="sxs-lookup"><span data-stu-id="7e069-124">The amount of time the Queue Reader Agent has run in this session.</span></span> <span data-ttu-id="7e069-125">El tiempo representa el tiempo transcurrido si el agente se está ejecutando, y el tiempo total de la sesión si la sesión del agente ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="7e069-125">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="7e069-126">**Mensaje de error**</span><span class="sxs-lookup"><span data-stu-id="7e069-126">**Error Message**</span></span>  
 <span data-ttu-id="7e069-127">Si una sesión finalizó con un error, este campo muestra el último mensaje de error registrado por el Agente de lectura de cola.</span><span class="sxs-lookup"><span data-stu-id="7e069-127">If a session ended in an error, this field displays the last error message logged by the Queue Reader Agent.</span></span> <span data-ttu-id="7e069-128">Si la sesión no ha finalizado con error, el campo se mostrará vacío.</span><span class="sxs-lookup"><span data-stu-id="7e069-128">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="7e069-129">**Mensaje de la acción**</span><span class="sxs-lookup"><span data-stu-id="7e069-129">**Action Message**</span></span>  
 <span data-ttu-id="7e069-130">Muestra todos los mensajes informativos y los mensajes con error que el Agente de lectura de cola ha registrado durante la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7e069-130">All informational messages and error messages that the Queue Reader Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="7e069-131">**Hora de la acción**</span><span class="sxs-lookup"><span data-stu-id="7e069-131">**Action Time**</span></span>  
 <span data-ttu-id="7e069-132">Muestra la hora de realización de la acción descrita en la columna **Mensaje de la acción** .</span><span class="sxs-lookup"><span data-stu-id="7e069-132">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="7e069-133">**Detalles del error o mensaje de la sesión seleccionada**</span><span class="sxs-lookup"><span data-stu-id="7e069-133">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="7e069-134">Solo se muestra si la sesión seleccionada presenta un valor de **Error** en la columna **Estado** .</span><span class="sxs-lookup"><span data-stu-id="7e069-134">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="7e069-135">El área de texto muestra la información detallada del error y el comando que se intentaba ejecutar en el momento de producirse el error.</span><span class="sxs-lookup"><span data-stu-id="7e069-135">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="7e069-136">También incluye vínculos a la información adicional relativa al error.</span><span class="sxs-lookup"><span data-stu-id="7e069-136">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e069-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e069-137">See Also</span></span>  
 <span data-ttu-id="7e069-138">[Iniciar el Monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="7e069-138">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="7e069-139">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="7e069-139">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="7e069-140">[Monitoring Replication](monitoring-replication.md)  (Supervisar la replicación)</span><span class="sxs-lookup"><span data-stu-id="7e069-140">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="7e069-141">Información general sobre los agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="7e069-141">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
