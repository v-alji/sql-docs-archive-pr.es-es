---
title: Agente de registro del LOG | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.logreaderagent.f1
helpviewer_keywords:
- Log Reader Agent dialog box
ms.assetid: 300a3c46-0e48-4334-99c0-9ee690d2ef4f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2b908e43cf97350fee2913e8cc6bab30a1bcd0dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749224"
---
# <a name="log-reader-agent"></a><span data-ttu-id="07903-102">Agente de registro del LOG</span><span class="sxs-lookup"><span data-stu-id="07903-102">Log Reader Agent</span></span>
  <span data-ttu-id="07903-103">El cuadro de diálogo **Agente de registro del LOG** muestra información detallada del Agente de registro del LOG, incluido el estado, el historial, los mensajes informativos y los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="07903-103">The **Log Reader Agent** dialog box displays detailed information on the Log Reader Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="07903-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="07903-104">Options</span></span>  
 <span data-ttu-id="07903-105">Seleccione las sesiones del Agente de registro del LOG que se van a ver en el menú **Ver** y, a continuación, seleccione una sesión específica en la cuadrícula con la etiqueta **Sesiones del Agente de registro del LOG**.</span><span class="sxs-lookup"><span data-stu-id="07903-105">Select which Log Reader Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Log Reader Agent**.</span></span> <span data-ttu-id="07903-106">En la cuadrícula con la etiqueta **Acciones en la sesión seleccionada**se muestra información detallada de la sesión.</span><span class="sxs-lookup"><span data-stu-id="07903-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="07903-107">Si la sesión seleccionada finalizó con un error, también se muestra el área de texto con la etiqueta **Detalles del error o mensaje de la sesión seleccionada** .</span><span class="sxs-lookup"><span data-stu-id="07903-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="07903-108">**Vista**</span><span class="sxs-lookup"><span data-stu-id="07903-108">**View**</span></span>  
 <span data-ttu-id="07903-109">Seleccione las sesiones del Agente de registro del LOG que se van a ver.</span><span class="sxs-lookup"><span data-stu-id="07903-109">Select which Log Reader Agent sessions to view.</span></span> <span data-ttu-id="07903-110">Normalmente, el Agente de registro del LOG se ejecuta sin interrupción, por lo que es posible que solo haya una sesión para ver.</span><span class="sxs-lookup"><span data-stu-id="07903-110">The Log Reader Agent typically runs continuously, therefore there might be only one session to view.</span></span>  
  
 <span data-ttu-id="07903-111">**Estado**</span><span class="sxs-lookup"><span data-stu-id="07903-111">**Status**</span></span>  
 <span data-ttu-id="07903-112">Indica el estado del Agente de registro del LOG.</span><span class="sxs-lookup"><span data-stu-id="07903-112">The status of the Log Reader Agent.</span></span> <span data-ttu-id="07903-113">En la lista siguiente se muestran los valores de estado posibles:</span><span class="sxs-lookup"><span data-stu-id="07903-113">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="07903-114">Error</span><span class="sxs-lookup"><span data-stu-id="07903-114">Error</span></span>  
  
-   <span data-ttu-id="07903-115">Reintentando comandos con errores</span><span class="sxs-lookup"><span data-stu-id="07903-115">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="07903-116">No está en ejecución</span><span class="sxs-lookup"><span data-stu-id="07903-116">Not running</span></span>  
  
-   <span data-ttu-id="07903-117">En ejecución</span><span class="sxs-lookup"><span data-stu-id="07903-117">Running</span></span>  
  
 <span data-ttu-id="07903-118">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="07903-118">**Start Time**</span></span>  
 <span data-ttu-id="07903-119">Muestra la hora de inicio de la sesión.</span><span class="sxs-lookup"><span data-stu-id="07903-119">The start time of the session.</span></span>  
  
 <span data-ttu-id="07903-120">**Hora de finalización**</span><span class="sxs-lookup"><span data-stu-id="07903-120">**End Time**</span></span>  
 <span data-ttu-id="07903-121">Muestra la hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="07903-121">The end time of the session.</span></span> <span data-ttu-id="07903-122">Si no se ha detenido el agente, el campo se mostrará vacío.</span><span class="sxs-lookup"><span data-stu-id="07903-122">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="07903-123">**Duration**</span><span class="sxs-lookup"><span data-stu-id="07903-123">**Duration**</span></span>  
 <span data-ttu-id="07903-124">Período de tiempo durante el que se ha ejecutado el Agente de registro del LOG en esta sesión.</span><span class="sxs-lookup"><span data-stu-id="07903-124">The amount of time the Log Reader Agent has run in this session.</span></span> <span data-ttu-id="07903-125">El tiempo representa el tiempo transcurrido si el agente se está ejecutando, y el tiempo total de la sesión si la sesión del agente ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="07903-125">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="07903-126">**Mensaje de error**</span><span class="sxs-lookup"><span data-stu-id="07903-126">**Error Message**</span></span>  
 <span data-ttu-id="07903-127">Si una sesión ha finalizado con un error, este campo muestra el último mensaje de error registrado por el Agente de registro del LOG.</span><span class="sxs-lookup"><span data-stu-id="07903-127">If a session ended in an error, this field displays the last error message logged by the Log Reader Agent.</span></span> <span data-ttu-id="07903-128">Si la sesión no ha finalizado con error, el campo se mostrará vacío.</span><span class="sxs-lookup"><span data-stu-id="07903-128">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="07903-129">**Mensaje de la acción**</span><span class="sxs-lookup"><span data-stu-id="07903-129">**Action Message**</span></span>  
 <span data-ttu-id="07903-130">Muestra todos los mensajes informativos y los mensajes de error que ha registrado el Agente de registro del LOG durante la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="07903-130">All informational messages and error messages that the Log Reader Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="07903-131">**Hora de la acción**</span><span class="sxs-lookup"><span data-stu-id="07903-131">**Action Time**</span></span>  
 <span data-ttu-id="07903-132">Muestra la hora de realización de la acción descrita en la columna **Mensaje de la acción** .</span><span class="sxs-lookup"><span data-stu-id="07903-132">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="07903-133">**Detalles del error o mensaje de la sesión seleccionada**</span><span class="sxs-lookup"><span data-stu-id="07903-133">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="07903-134">Solo se muestra si la sesión seleccionada presenta un valor de **Error** en la columna **Estado** .</span><span class="sxs-lookup"><span data-stu-id="07903-134">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="07903-135">El área de texto muestra la información detallada del error y el comando que se intentaba ejecutar en el momento de producirse el error.</span><span class="sxs-lookup"><span data-stu-id="07903-135">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="07903-136">También incluye vínculos a la información adicional relativa al error.</span><span class="sxs-lookup"><span data-stu-id="07903-136">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07903-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07903-137">See Also</span></span>  
 <span data-ttu-id="07903-138">[Iniciar el Monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="07903-138">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="07903-139">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="07903-139">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="07903-140">[Monitoring Replication](monitoring-replication.md)  (Supervisar la replicación)</span><span class="sxs-lookup"><span data-stu-id="07903-140">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="07903-141">Información general sobre los agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="07903-141">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
