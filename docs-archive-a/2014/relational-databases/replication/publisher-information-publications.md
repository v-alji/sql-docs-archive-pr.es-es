---
title: Cuadro de diálogo Replicación de SQL Server ' información del publicador ' | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.publications.f1
ms.assetid: 0b2e3d4e-03b7-4c31-8f96-48648d750010
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d3797ae4f9fe8f42b4abec715c63bc627c2a62cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745191"
---
# <a name="sql-server-replication-publisher-information-dialog-box"></a><span data-ttu-id="db27e-102">Replicación de SQL Server cuadro de diálogo ' información del publicador '</span><span class="sxs-lookup"><span data-stu-id="db27e-102">SQL Server Replication 'Publisher Information' dialog box</span></span>
  <span data-ttu-id="db27e-103">La pestaña **Publicaciones** proporciona información de resumen para todas las publicaciones del publicador seleccionado en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="db27e-103">The **Publications** tab provides summary information for all publications at the Publisher selected in the left pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="db27e-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="db27e-104">Options</span></span>  
 <span data-ttu-id="db27e-105">Para cambiar la manera que la cuadrícula muestra los datos, haga clic con el botón secundario en la cuadrícula y, a continuación, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="db27e-105">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="db27e-106">**Ordenar**: ordene en una o más columnas en el cuadro de diálogo **Ordenar columnas** .</span><span class="sxs-lookup"><span data-stu-id="db27e-106">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="db27e-107">**Elegir columnas para mostrar**: seleccione las columnas que se mostrarán y el orden en el que se mostrarán en el cuadro de diálogo **Elegir columnas** .</span><span class="sxs-lookup"><span data-stu-id="db27e-107">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="db27e-108">**Filtro**: filtre filas en la cuadrícula basándose en los valores de columna en el cuadro de diálogo **Configuración del filtro** .</span><span class="sxs-lookup"><span data-stu-id="db27e-108">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="db27e-109">**Borrar filtro**: borre cualquier configuración de filtro para la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="db27e-109">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="db27e-110">La configuración del filtro es específica de cada cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="db27e-110">Filter settings are specific to each grid.</span></span> <span data-ttu-id="db27e-111">La selección y ordenación de las columnas se aplica a todas las cuadrículas del mismo tipo, como la cuadrícula de las publicaciones para cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="db27e-111">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="db27e-112">**Estado**</span><span class="sxs-lookup"><span data-stu-id="db27e-112">**Status**</span></span>  
 <span data-ttu-id="db27e-113">Estado de cada publicación que se determina mediante el estado de prioridad más alto de sus suscripciones.</span><span class="sxs-lookup"><span data-stu-id="db27e-113">The status of each publication, which is determined by the highest priority status of its subscriptions.</span></span> <span data-ttu-id="db27e-114">De forma predeterminada, la cuadrícula que contiene información de publicación se ordena por la columna **Estado** .</span><span class="sxs-lookup"><span data-stu-id="db27e-114">By default, the grid containing publication information is sorted by the **Status** column.</span></span> <span data-ttu-id="db27e-115">La siguiente lista muestra los posibles valores de estado y el orden de los valores (por ejemplo, los errores siempre se muestran en la parte superior de la cuadrícula).</span><span class="sxs-lookup"><span data-stu-id="db27e-115">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid):</span></span>  
  
-   <span data-ttu-id="db27e-116">Error</span><span class="sxs-lookup"><span data-stu-id="db27e-116">Error</span></span>  
  
-   <span data-ttu-id="db27e-117">Rendimiento crítico</span><span class="sxs-lookup"><span data-stu-id="db27e-117">Performance critical</span></span>  
  
-   <span data-ttu-id="db27e-118">Reintentando comando con errores</span><span class="sxs-lookup"><span data-stu-id="db27e-118">Retrying failed command</span></span>  
  
-   <span data-ttu-id="db27e-119">Aceptar</span><span class="sxs-lookup"><span data-stu-id="db27e-119">OK</span></span>  
  
 <span data-ttu-id="db27e-120">El valor de estado **Rendimiento crítico** es importante para las suscripciones transaccionales y de mezcla; en el caso de las suscripciones transaccionales, este valor solamente se puede mostrar si se establece un umbral.</span><span class="sxs-lookup"><span data-stu-id="db27e-120">The status value **Performance critical** is relevant for transactional subscriptions and merge subscriptions; for transactional subscriptions, it can be displayed only if a threshold is set.</span></span> <span data-ttu-id="db27e-121">Para obtener información sobre la medición del rendimiento y el establecimiento de umbrales, vea [Supervisar el rendimiento con el Monitor de replicación](monitor/monitor-performance-with-replication-monitor.md) y [Establecer umbrales y advertencias en el Monitor de replicación](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="db27e-121">For information on performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="db27e-122">**Publicación**</span><span class="sxs-lookup"><span data-stu-id="db27e-122">**Publication**</span></span>  
 <span data-ttu-id="db27e-123">El nombre de cada publicación, con el formato *nombreDeBaseDeDatosDePublicación: nombreDePublicación*.</span><span class="sxs-lookup"><span data-stu-id="db27e-123">The name of each publication, in the form *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="db27e-124">**Suscripciones**</span><span class="sxs-lookup"><span data-stu-id="db27e-124">**Subscriptions**</span></span>  
 <span data-ttu-id="db27e-125">El número de suscripciones para cada publicación.</span><span class="sxs-lookup"><span data-stu-id="db27e-125">The number of subscriptions for each publication.</span></span>  
  
 <span data-ttu-id="db27e-126">**Sincronizando**</span><span class="sxs-lookup"><span data-stu-id="db27e-126">**Synchronizing**</span></span>  
 <span data-ttu-id="db27e-127">El número de suscripciones para cada publicación que se están sincronizando actualmente.</span><span class="sxs-lookup"><span data-stu-id="db27e-127">The number of subscriptions for each publication that are currently synchronizing:</span></span>  
  
-   <span data-ttu-id="db27e-128">Para la replicación transaccional, "sincronizando" significa que el Agente de distribución está en ejecución, pero que no necesariamente se está creando una replicación de los datos.</span><span class="sxs-lookup"><span data-stu-id="db27e-128">For transactional replication, "synchronizing" means that the Distribution Agent is running, but data is not necessarily being replicated.</span></span>  
  
-   <span data-ttu-id="db27e-129">Para la replicación de mezcla, "sincronizando" significa que el Agente de mezcla está en ejecución y que se está creando una replicación de los datos.</span><span class="sxs-lookup"><span data-stu-id="db27e-129">For merge replication, "synchronizing" means that the Merge Agent is running and that data is currently being replicated.</span></span>  
  
-   <span data-ttu-id="db27e-130">Para la replicación de instantáneas, "sincronizando" significa que el Agente de distribución está en ejecución y que se está creando una replicación de los datos.</span><span class="sxs-lookup"><span data-stu-id="db27e-130">For snapshot replication, "synchronizing" means that the Distribution Agent is running and that data is currently being replicated.</span></span>  
  
 <span data-ttu-id="db27e-131">**Rendimiento medio actual** y **Peor rendimiento actual**</span><span class="sxs-lookup"><span data-stu-id="db27e-131">**Current Average Performance** and **Current Worst Performance**</span></span>  
 <span data-ttu-id="db27e-132">Solo para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="db27e-132">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="db27e-133">Clasificación de rendimiento medio y clasificación de peor rendimiento, respectivamente, correspondientes a todas las suscripciones de una publicación.</span><span class="sxs-lookup"><span data-stu-id="db27e-133">The average performance rating and the worst performance rating, respectively, for all subscriptions to a publication.</span></span> <span data-ttu-id="db27e-134">Las clasificaciones se basan en las medidas más recientes tomadas por el Monitor de replicación y no reflejan el rendimiento posterior de una suscripción.</span><span class="sxs-lookup"><span data-stu-id="db27e-134">Ratings are based on the most recent measurements taken by Replication Monitor and do not reflect the performance of a subscription over time.</span></span>  
  
 <span data-ttu-id="db27e-135">En la replicación transaccional, el Monitor de replicación solamente muestra un valor para las publicaciones cuyos umbrales de rendimiento están definidos.</span><span class="sxs-lookup"><span data-stu-id="db27e-135">For transactional replication, Replication Monitor displays a value only for publications that have performance thresholds defined.</span></span> <span data-ttu-id="db27e-136">Si no se han definido umbrales de rendimiento para una publicación, en esta columna se muestra **No habilitado**.</span><span class="sxs-lookup"><span data-stu-id="db27e-136">If performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="db27e-137">En la replicación de mezcla, el Monitor de replicación muestra un valor una vez que se han producido cinco sincronizaciones con al menos 50 cambios en cada una a través del mismo tipo de conexión (de acceso telefónico o LAN).</span><span class="sxs-lookup"><span data-stu-id="db27e-137">For merge replication, Replication Monitor displays a value after five synchronizations have occurred with 50 or more changes each over the same type of connection (dial-up or LAN).</span></span> <span data-ttu-id="db27e-138">Si ha habido menos de cinco sincronizaciones con al menos 50 cambios, o la sincronización más reciente tiene menos de 50 cambios, está columna está en blanco.</span><span class="sxs-lookup"><span data-stu-id="db27e-138">If there have been less than five synchronizations with 50 or more changes or the most recent synchronization has less than 50 changes, this column is blank.</span></span>  
  
 <span data-ttu-id="db27e-139">La clasificación de rendimiento tiene uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="db27e-139">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="db27e-140">Excelente</span><span class="sxs-lookup"><span data-stu-id="db27e-140">Excellent</span></span>  
  
-   <span data-ttu-id="db27e-141">Bueno</span><span class="sxs-lookup"><span data-stu-id="db27e-141">Good</span></span>  
  
-   <span data-ttu-id="db27e-142">Regular</span><span class="sxs-lookup"><span data-stu-id="db27e-142">Fair</span></span>  
  
-   <span data-ttu-id="db27e-143">Insuficiente</span><span class="sxs-lookup"><span data-stu-id="db27e-143">Poor</span></span>  
  
-   <span data-ttu-id="db27e-144">Crítico</span><span class="sxs-lookup"><span data-stu-id="db27e-144">Critical</span></span>  
  
 <span data-ttu-id="db27e-145">Para obtener más información sobre cómo se definen las clasificaciones de rendimiento y cómo se establecen los umbrales de rendimiento, vea [Supervisar el rendimiento con el Monitor de replicación](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="db27e-145">For more information about how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db27e-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db27e-146">See Also</span></span>  
 <span data-ttu-id="db27e-147">[Iniciar el Monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="db27e-147">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="db27e-148">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="db27e-148">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="db27e-149">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="db27e-149">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
