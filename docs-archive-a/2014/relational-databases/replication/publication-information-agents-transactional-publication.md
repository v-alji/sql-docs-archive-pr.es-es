---
title: Información de publicación, Agentes (Publicación transaccional) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.downlevelagents.tran.f1
ms.assetid: 38ef2f54-53bb-4053-876d-86f8f06a4519
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1a3d50da15ea653a7911e65ad888d5997f47a3f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662808"
---
# <a name="publication-information-agents-transactional-publication"></a><span data-ttu-id="6ceda-102">Información de publicación, Agentes (Publicación transaccional)</span><span class="sxs-lookup"><span data-stu-id="6ceda-102">Publication Information, Agents (Transactional Publication)</span></span>
  <span data-ttu-id="6ceda-103">La pestaña **Agentes** muestra información resumida de los agentes para la publicación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6ceda-103">The **Agents** tab displays summary information on the agents for the selected publication.</span></span> <span data-ttu-id="6ceda-104">La información del Agente de instantáneas y el Agente de registro del LOG se muestra para todas las publicaciones transaccionales.</span><span class="sxs-lookup"><span data-stu-id="6ceda-104">Information on the Snapshot Agent and Log Reader Agent is displayed for all transactional publications.</span></span> <span data-ttu-id="6ceda-105">La información del Agente de lectura de cola se muestra para las publicaciones transaccionales que están habilitadas para las suscripciones de actualización en cola.</span><span class="sxs-lookup"><span data-stu-id="6ceda-105">Information on the Queue Reader Agent is displayed for those transactional publications that are enabled for queued updating subscriptions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6ceda-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="6ceda-106">Options</span></span>  
 <span data-ttu-id="6ceda-107">Para obtener información más detallada y las tareas relacionadas con un agente, haga clic con el botón secundario en la fila de ese agente y, a continuación, haga clic en una opción del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="6ceda-107">For more detailed information and tasks related to an agent, right-click the row for that agent, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="6ceda-108">Para cambiar la manera que la cuadrícula muestra los datos, haga clic con el botón secundario en la cuadrícula y, a continuación, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6ceda-108">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="6ceda-109">**Ordenar**: ordene en una o más columnas en el cuadro de diálogo **Ordenar columnas** .</span><span class="sxs-lookup"><span data-stu-id="6ceda-109">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="6ceda-110">**Elegir columnas para mostrar**: seleccione las columnas que se mostrarán y el orden en el que se mostrarán en el cuadro de diálogo **Elegir columnas** .</span><span class="sxs-lookup"><span data-stu-id="6ceda-110">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="6ceda-111">**Filtro**: filtre filas en la cuadrícula basándose en los valores de columna en el cuadro de diálogo **Configuración del filtro** .</span><span class="sxs-lookup"><span data-stu-id="6ceda-111">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="6ceda-112">**Borrar filtro**: borre cualquier configuración de filtro para la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="6ceda-112">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="6ceda-113">La configuración del filtro es específica de cada cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="6ceda-113">Filter settings are specific to each grid.</span></span> <span data-ttu-id="6ceda-114">La selección y ordenación de las columnas se aplica a todas las cuadrículas del mismo tipo, como la cuadrícula de las publicaciones para cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="6ceda-114">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="6ceda-115">**Estado**</span><span class="sxs-lookup"><span data-stu-id="6ceda-115">**Status**</span></span>  
 <span data-ttu-id="6ceda-116">Estado de cada agente de replicación asociado con la publicación.</span><span class="sxs-lookup"><span data-stu-id="6ceda-116">The status of each replication agent associated with the publication.</span></span> <span data-ttu-id="6ceda-117">En la lista siguiente se muestran los valores de estado posibles:</span><span class="sxs-lookup"><span data-stu-id="6ceda-117">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="6ceda-118">Error</span><span class="sxs-lookup"><span data-stu-id="6ceda-118">Error</span></span>  
  
-   <span data-ttu-id="6ceda-119">Reintentando comandos con errores</span><span class="sxs-lookup"><span data-stu-id="6ceda-119">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="6ceda-120">No está en ejecución</span><span class="sxs-lookup"><span data-stu-id="6ceda-120">Not running</span></span>  
  
-   <span data-ttu-id="6ceda-121">En ejecución</span><span class="sxs-lookup"><span data-stu-id="6ceda-121">Running</span></span>  
  
-   <span data-ttu-id="6ceda-122">Completed</span><span class="sxs-lookup"><span data-stu-id="6ceda-122">Completed</span></span>  
  
 <span data-ttu-id="6ceda-123">**Agent**</span><span class="sxs-lookup"><span data-stu-id="6ceda-123">**Agent**</span></span>  
 <span data-ttu-id="6ceda-124">Nombre de cada agente de replicación asociado con la publicación.</span><span class="sxs-lookup"><span data-stu-id="6ceda-124">The name of each replication agent associated with the publication.</span></span> <span data-ttu-id="6ceda-125">El Agente de distribución está asociado con suscripciones a esta publicación.</span><span class="sxs-lookup"><span data-stu-id="6ceda-125">The Distribution Agent is associated with subscriptions to this publication.</span></span> <span data-ttu-id="6ceda-126">Para más información, vea [Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="6ceda-126">For more information, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="6ceda-127">**Última hora de inicio**</span><span class="sxs-lookup"><span data-stu-id="6ceda-127">**Last Start Time**</span></span>  
 <span data-ttu-id="6ceda-128">Hora en la que se inició el agente por última vez.</span><span class="sxs-lookup"><span data-stu-id="6ceda-128">The last time the agent started.</span></span>  
  
 <span data-ttu-id="6ceda-129">**Duration**</span><span class="sxs-lookup"><span data-stu-id="6ceda-129">**Duration**</span></span>  
 <span data-ttu-id="6ceda-130">Tiempo durante el que se ha ejecutado el agente.</span><span class="sxs-lookup"><span data-stu-id="6ceda-130">The amount of time the agent has run.</span></span> <span data-ttu-id="6ceda-131">Este tiempo representa el tiempo transcurrido si el agente se está ejecutando actualmente o el tiempo total de ejecución si ya finalizó la ejecución.</span><span class="sxs-lookup"><span data-stu-id="6ceda-131">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="6ceda-132">**Última acción**</span><span class="sxs-lookup"><span data-stu-id="6ceda-132">**Last Action**</span></span>  
 <span data-ttu-id="6ceda-133">La última acción realizada durante la ejecución más reciente del agente.</span><span class="sxs-lookup"><span data-stu-id="6ceda-133">The last action performed during the most recent run of the agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ceda-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ceda-134">See Also</span></span>  
 <span data-ttu-id="6ceda-135">[Iniciar el monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="6ceda-135">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="6ceda-136">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="6ceda-136">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="6ceda-137">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="6ceda-137">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
