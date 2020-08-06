---
title: Suscripción, Historial de Distribuidor a suscriptor (suscripción de instantánea) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.pubtodist.snapshot.f1
ms.assetid: d3575964-f287-4bcf-8d2e-f81a33141b25
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fe894e23e7ad7fef9c328334740eff73164130a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749694"
---
# <a name="subscription-distributor-to-subscriber-history-snapshot-subscription"></a><span data-ttu-id="31ecc-102">Suscripción, Historial de Distribuidor a suscriptor (suscripción de instantánea)</span><span class="sxs-lookup"><span data-stu-id="31ecc-102">Subscription, Distributor to Subscriber History (Snapshot Subscription)</span></span>
  <span data-ttu-id="31ecc-103">La pestaña **Historial de Distribuidor a suscriptor** muestra información detallada sobre el Agente de distribución, incluidos el estado, el historial, los mensajes informativos y cualquier mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="31ecc-103">The **Distributor to Subscriber History** tab displays detailed information on the Distribution Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="31ecc-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="31ecc-104">Options</span></span>  
 <span data-ttu-id="31ecc-105">Seleccione las sesiones del Agente de distribución que desee ver en el menú **Ver** y, a continuación, seleccione una sesión concreta en la cuadrícula etiquetada como **Sesiones del Agente de distribución**.</span><span class="sxs-lookup"><span data-stu-id="31ecc-105">Select which Distribution Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Distribution Agent**.</span></span> <span data-ttu-id="31ecc-106">En la cuadrícula con la etiqueta **Acciones en la sesión seleccionada**se muestra información detallada de la sesión.</span><span class="sxs-lookup"><span data-stu-id="31ecc-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="31ecc-107">Si la sesión seleccionada finalizó con un error, también se muestra el área de texto con la etiqueta **Detalles del error o mensaje de la sesión seleccionada** .</span><span class="sxs-lookup"><span data-stu-id="31ecc-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="31ecc-108">**Ver**</span><span class="sxs-lookup"><span data-stu-id="31ecc-108">**View**</span></span>  
 <span data-ttu-id="31ecc-109">Seleccione las sesiones del Agente de distribución que desee ver.</span><span class="sxs-lookup"><span data-stu-id="31ecc-109">Select which Distribution Agent sessions to view.</span></span>  
  
 <span data-ttu-id="31ecc-110">**Estado**</span><span class="sxs-lookup"><span data-stu-id="31ecc-110">**Status**</span></span>  
 <span data-ttu-id="31ecc-111">Estado del Agente de distribución.</span><span class="sxs-lookup"><span data-stu-id="31ecc-111">The status of the Distribution Agent.</span></span> <span data-ttu-id="31ecc-112">En la lista siguiente se muestran los valores de estado posibles:</span><span class="sxs-lookup"><span data-stu-id="31ecc-112">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="31ecc-113">Error</span><span class="sxs-lookup"><span data-stu-id="31ecc-113">Error</span></span>  
  
-   <span data-ttu-id="31ecc-114">Completed</span><span class="sxs-lookup"><span data-stu-id="31ecc-114">Completed</span></span>  
  
-   <span data-ttu-id="31ecc-115">Intentando de nuevo</span><span class="sxs-lookup"><span data-stu-id="31ecc-115">Retrying</span></span>  
  
-   <span data-ttu-id="31ecc-116">En ejecución</span><span class="sxs-lookup"><span data-stu-id="31ecc-116">Running</span></span>  
  
 <span data-ttu-id="31ecc-117">**Hora de inicio**</span><span class="sxs-lookup"><span data-stu-id="31ecc-117">**Start Time**</span></span>  
 <span data-ttu-id="31ecc-118">Muestra la hora de inicio de la sesión.</span><span class="sxs-lookup"><span data-stu-id="31ecc-118">The start time of the session.</span></span>  
  
 <span data-ttu-id="31ecc-119">**Hora de finalización**</span><span class="sxs-lookup"><span data-stu-id="31ecc-119">**End Time**</span></span>  
 <span data-ttu-id="31ecc-120">Muestra la hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="31ecc-120">The end time of the session.</span></span> <span data-ttu-id="31ecc-121">Si no se ha detenido el agente, el campo se mostrará vacío.</span><span class="sxs-lookup"><span data-stu-id="31ecc-121">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="31ecc-122">**Duration**</span><span class="sxs-lookup"><span data-stu-id="31ecc-122">**Duration**</span></span>  
 <span data-ttu-id="31ecc-123">Cantidad de tiempo que se ha ejecutado el Agente de distribución en esta sesión.</span><span class="sxs-lookup"><span data-stu-id="31ecc-123">The amount of time the Distribution Agent has run in this session.</span></span> <span data-ttu-id="31ecc-124">El tiempo representa el tiempo transcurrido si el agente se encuentra en ejecución, y el tiempo total de la sesión si la sesión del agente ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="31ecc-124">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session had ended.</span></span>  
  
 <span data-ttu-id="31ecc-125">**Mensaje de error**</span><span class="sxs-lookup"><span data-stu-id="31ecc-125">**Error Message**</span></span>  
 <span data-ttu-id="31ecc-126">Si una sesión terminó en error, este campo muestra el último mensaje de error registrado por el Agente de distribución.</span><span class="sxs-lookup"><span data-stu-id="31ecc-126">If a session ended in an error, this field displays the last error message logged by the Distribution Agent.</span></span> <span data-ttu-id="31ecc-127">Si la sesión no ha finalizado con error, el campo se mostrará vacío.</span><span class="sxs-lookup"><span data-stu-id="31ecc-127">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="31ecc-128">**Mensaje de la acción**</span><span class="sxs-lookup"><span data-stu-id="31ecc-128">**Action Message**</span></span>  
 <span data-ttu-id="31ecc-129">Todos los mensajes informativos y de error que el Agente de distribución ha registrado durante la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="31ecc-129">All informational messages and error messages that the Distribution Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="31ecc-130">**Hora de la acción**</span><span class="sxs-lookup"><span data-stu-id="31ecc-130">**Action Time**</span></span>  
 <span data-ttu-id="31ecc-131">Muestra la hora de realización de la acción descrita en la columna **Mensaje de la acción** .</span><span class="sxs-lookup"><span data-stu-id="31ecc-131">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="31ecc-132">**Detalles del error o mensaje de la sesión seleccionada**</span><span class="sxs-lookup"><span data-stu-id="31ecc-132">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="31ecc-133">Solo se muestra si la sesión seleccionada presenta un valor de **Error** en la columna **Estado** .</span><span class="sxs-lookup"><span data-stu-id="31ecc-133">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="31ecc-134">El área de texto muestra la información detallada del error y el comando que se intentaba ejecutar en el momento de producirse el error.</span><span class="sxs-lookup"><span data-stu-id="31ecc-134">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="31ecc-135">También incluye vínculos a la información adicional relativa al error.</span><span class="sxs-lookup"><span data-stu-id="31ecc-135">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31ecc-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31ecc-136">See Also</span></span>  
 <span data-ttu-id="31ecc-137">[Iniciar el monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="31ecc-137">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="31ecc-138">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="31ecc-138">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="31ecc-139">[Monitoring Replication](monitoring-replication.md)  (Supervisar la replicación)</span><span class="sxs-lookup"><span data-stu-id="31ecc-139">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="31ecc-140">Información general sobre los agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="31ecc-140">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
