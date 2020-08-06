---
title: Agente de instantáneas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.snapshotagent.f1
helpviewer_keywords:
- Snapshot Agent dialog box
ms.assetid: b715e621-2cd5-4a15-8f58-a341aa8ef5e4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 925f2d3841b5dded6c8504a4a05dc60e61024161
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677535"
---
# <a name="snapshot-agent"></a><span data-ttu-id="2fa2c-102">Agente de instantáneas</span><span class="sxs-lookup"><span data-stu-id="2fa2c-102">Snapshot Agent</span></span>
  <span data-ttu-id="2fa2c-103">El cuadro de diálogo **Agente de instantáneas** muestra información detallada acerca del Agente de instantáneas, como el estado, el historial, mensajes informativos y mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-103">The **Snapshot Agent** dialog box displays detailed information on the Snapshot Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2fa2c-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="2fa2c-104">Options</span></span>  
 <span data-ttu-id="2fa2c-105">Seleccione en el menú **Ver** las sesiones del Agente de instantáneas que desea ver y seleccione a continuación una sesión específica en la cuadrícula con la etiqueta **Sesiones del Agente de instantáneas**.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-105">Select which Snapshot Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Snapshot Agent**.</span></span> <span data-ttu-id="2fa2c-106">En la cuadrícula con la etiqueta **Acciones en la sesión seleccionada**se muestra información detallada de la sesión.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="2fa2c-107">Si la sesión seleccionada finalizó con un error, también se muestra el área de texto con la etiqueta **Detalles del error o mensaje de la sesión seleccionada** .</span><span class="sxs-lookup"><span data-stu-id="2fa2c-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="2fa2c-108">**Vista**</span><span class="sxs-lookup"><span data-stu-id="2fa2c-108">**View**</span></span>  
 <span data-ttu-id="2fa2c-109">Seleccione las sesiones del Agente de instantáneas que desea ver.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-109">Select which Snapshot Agent sessions to view.</span></span>  
  
 <span data-ttu-id="2fa2c-110">**Estado**</span><span class="sxs-lookup"><span data-stu-id="2fa2c-110">**Status**</span></span>  
 <span data-ttu-id="2fa2c-111">Estado del Agente de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-111">The status of the Snapshot Agent.</span></span> <span data-ttu-id="2fa2c-112">En la lista siguiente se muestran los valores de estado posibles:</span><span class="sxs-lookup"><span data-stu-id="2fa2c-112">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="2fa2c-113">Error</span><span class="sxs-lookup"><span data-stu-id="2fa2c-113">Error</span></span>  
  
-   <span data-ttu-id="2fa2c-114">Reintentando comandos con errores</span><span class="sxs-lookup"><span data-stu-id="2fa2c-114">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="2fa2c-115">No está en ejecución</span><span class="sxs-lookup"><span data-stu-id="2fa2c-115">Not running</span></span>  
  
-   <span data-ttu-id="2fa2c-116">Completed</span><span class="sxs-lookup"><span data-stu-id="2fa2c-116">Completed</span></span>  
  
 <span data-ttu-id="2fa2c-117">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="2fa2c-117">**Start Time**</span></span>  
 <span data-ttu-id="2fa2c-118">Muestra la hora de inicio de la sesión.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-118">The start time of the session.</span></span>  
  
 <span data-ttu-id="2fa2c-119">**Hora de finalización**</span><span class="sxs-lookup"><span data-stu-id="2fa2c-119">**End Time**</span></span>  
 <span data-ttu-id="2fa2c-120">Muestra la hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-120">The end time of the session.</span></span> <span data-ttu-id="2fa2c-121">Si no se ha detenido el agente, el campo se mostrará vacío.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-121">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="2fa2c-122">**Duration**</span><span class="sxs-lookup"><span data-stu-id="2fa2c-122">**Duration**</span></span>  
 <span data-ttu-id="2fa2c-123">Muestra el tiempo que se ha ejecutado el Agente de instantáneas en esta sesión.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-123">The amount of time the Snapshot Agent has run in this session.</span></span> <span data-ttu-id="2fa2c-124">El tiempo representa el tiempo transcurrido si el agente se está ejecutando, y el tiempo total de la sesión si la sesión del agente ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-124">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="2fa2c-125">**Mensaje de error**</span><span class="sxs-lookup"><span data-stu-id="2fa2c-125">**Error Message**</span></span>  
 <span data-ttu-id="2fa2c-126">Si la sesión ha finalizado con error, el campo mostrará el último mensaje de error registrado en el Agente de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-126">If a session ended in an error, this field displays the last error message logged by the Snapshot Agent.</span></span> <span data-ttu-id="2fa2c-127">Si la sesión no ha finalizado con error, el campo se mostrará vacío.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-127">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="2fa2c-128">**Mensaje de la acción**</span><span class="sxs-lookup"><span data-stu-id="2fa2c-128">**Action Message**</span></span>  
 <span data-ttu-id="2fa2c-129">Muestra los mensajes informativos y de error registrados en el Agente de instantáneas durante la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-129">All informational messages and error messages that the Snapshot Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="2fa2c-130">**Hora de la acción**</span><span class="sxs-lookup"><span data-stu-id="2fa2c-130">**Action Time**</span></span>  
 <span data-ttu-id="2fa2c-131">Muestra la hora de realización de la acción descrita en la columna **Mensaje de la acción** .</span><span class="sxs-lookup"><span data-stu-id="2fa2c-131">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="2fa2c-132">**Detalles del error o mensaje de la sesión seleccionada**</span><span class="sxs-lookup"><span data-stu-id="2fa2c-132">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="2fa2c-133">Solo se muestra si la sesión seleccionada presenta un valor de **Error** en la columna **Estado** .</span><span class="sxs-lookup"><span data-stu-id="2fa2c-133">Is displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="2fa2c-134">El área de texto muestra la información detallada del error y el comando que se intentaba ejecutar en el momento de producirse el error.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-134">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="2fa2c-135">También incluye vínculos a la información adicional relativa al error.</span><span class="sxs-lookup"><span data-stu-id="2fa2c-135">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fa2c-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2fa2c-136">See Also</span></span>  
 <span data-ttu-id="2fa2c-137">[Iniciar el Monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="2fa2c-137">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="2fa2c-138">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="2fa2c-138">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="2fa2c-139">[Monitoring Replication](monitoring-replication.md)  (Supervisar la replicación)</span><span class="sxs-lookup"><span data-stu-id="2fa2c-139">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="2fa2c-140">Información general sobre los agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="2fa2c-140">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
