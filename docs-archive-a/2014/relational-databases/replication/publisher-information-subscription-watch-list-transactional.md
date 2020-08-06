---
title: Información del publicador, lista de supervisión de suscripciones (publicación transaccional, SQL Server 2005 y versiones posteriores) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.subscriptionssummary.tran.f1
ms.assetid: 6bc64ddb-5c86-4681-a391-77fc1d3c4e6e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bf6d151b75bca1dbfd2e5ad8f7601fb1002e84be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661906"
---
# <a name="publisher-information-subscription-watch-list-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="4dfc0-102">Información del publicador, Lista de supervisión de suscripciones (Publicación transaccional, SQL Server 2005 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="4dfc0-102">Publisher Information, Subscription Watch List (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="4dfc0-103">La pestaña **Lista de supervisión de suscripciones** está disponible para distribuidores que ejecutan SQL Server 2005 y versiones posteriores; está pensada para mostrar información sobre las suscripciones de todas las publicaciones disponibles en el publicador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-103">The **Subscription Watch List** tab is available for Distributors running SQL Server 2005 and later versions; it is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="4dfc0-104">Puede filtrar la lista de suscripciones para ver errores, advertencias y las suscripciones que tienen un rendimiento bajo.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-104">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="4dfc0-105">Esta pestaña proporciona una ubicación única para que un administrador supervise toda la actividad de replicación en un publicador: el Monitor de replicación muestra todas las suscripciones que necesitan atención, basándose en el tipo de replicación seleccionado y en la opción elegida en el cuadro de lista desplegable **Mostrar** .</span><span class="sxs-lookup"><span data-stu-id="4dfc0-105">This tab provides a single location for an administrator to monitor all replication activity at a Publisher: Replication Monitor displays all subscriptions that require attention, based on the selected replication type and on the option chosen in the **Show** drop-down list box.</span></span> <span data-ttu-id="4dfc0-106">Puesto que los elementos mostrados en esta pestaña se basan en el rendimiento y el estado actual, las suscripciones se muestran en esta página solo si coinciden con la opción del cuadro de lista **Mostrar** en el momento actual.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-106">Because the items displayed on this tab are based on current status and performance, subscriptions are displayed on this page only if they match the option in the **Show** list box at the current time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4dfc0-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="4dfc0-107">Options</span></span>  
 <span data-ttu-id="4dfc0-108">Para obtener información más detallada y las tareas de una suscripción, haga clic con el botón secundario en la fila de dicha suscripción y, a continuación, haga clic en una opción del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-108">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="4dfc0-109">Para cambiar la manera que la cuadrícula muestra los datos, haga clic con el botón secundario en la cuadrícula y, a continuación, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4dfc0-109">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="4dfc0-110">**Ordenar**: ordene en una o más columnas en el cuadro de diálogo **Ordenar columnas** .</span><span class="sxs-lookup"><span data-stu-id="4dfc0-110">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="4dfc0-111">**Elegir columnas para mostrar**: seleccione las columnas que se mostrarán y el orden en el que se mostrarán en el cuadro de diálogo **Elegir columnas** .</span><span class="sxs-lookup"><span data-stu-id="4dfc0-111">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="4dfc0-112">**Filtro**: filtre filas en la cuadrícula basándose en los valores de columna en el cuadro de diálogo **Configuración del filtro** .</span><span class="sxs-lookup"><span data-stu-id="4dfc0-112">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="4dfc0-113">**Borrar filtro**: borre cualquier configuración de filtro para la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-113">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="4dfc0-114">La configuración del filtro es específica de cada cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-114">Filter settings are specific to each grid.</span></span> <span data-ttu-id="4dfc0-115">La selección y ordenación de las columnas se aplica a todas las cuadrículas del mismo tipo, como la cuadrícula de las publicaciones para cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-115">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="4dfc0-116">**Mostrar suscripciones transaccionales**</span><span class="sxs-lookup"><span data-stu-id="4dfc0-116">**Show Transactional Subscriptions**</span></span>  
 <span data-ttu-id="4dfc0-117">Seleccione el tipo de suscripción (transaccional, de instantánea o de mezcla) que se mostrará para el publicador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-117">Select the type of subscriptions (transactional, snapshot, or merge) to display for the selected Publisher.</span></span>  
  
 <span data-ttu-id="4dfc0-118">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="4dfc0-118">**Show**</span></span>  
 <span data-ttu-id="4dfc0-119">Seleccione los estados de la suscripción que se mostrarán para el tipo de suscripción seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-119">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="4dfc0-120">Por ejemplo, puede seleccionar mostrar solo aquellas suscripciones que tienen errores.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-120">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="4dfc0-121">**Estado**</span><span class="sxs-lookup"><span data-stu-id="4dfc0-121">**Status**</span></span>  
 <span data-ttu-id="4dfc0-122">Es el estado de cada suscripción, determinado por el estado del Agente de distribución o el Agente de registro del LOG (se muestra el estado de prioridad más alto; el estado también se puede determinar mediante el Agente de lectura de cola si se utilizan suscripciones de actualización en cola).</span><span class="sxs-lookup"><span data-stu-id="4dfc0-122">The status of each subscription, which is determined by the status of the Distribution Agent or the Log Reader Agent (the higher priority status is displayed; the status can also be determined by the Queue Reader Agent if queued updating subscriptions are used).</span></span>  
  
 <span data-ttu-id="4dfc0-123">De forma predeterminada, la cuadrícula que contiene la información de suscripción está ordenada por la columna **Estado** (y, a continuación, por la columna **Rendimiento** de las suscripciones con el mismo estado).</span><span class="sxs-lookup"><span data-stu-id="4dfc0-123">By default, the grid containing subscription information is sorted by the **Status** column (and then sorted by the **Performance** column for those subscriptions with the same status).</span></span> <span data-ttu-id="4dfc0-124">La siguiente lista muestra los valores de estado posibles y el criterio de ordenación de los valores (por ejemplo, los errores se muestran siempre en la parte superior de la cuadrícula).</span><span class="sxs-lookup"><span data-stu-id="4dfc0-124">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="4dfc0-125">Error</span><span class="sxs-lookup"><span data-stu-id="4dfc0-125">Error</span></span>  
  
-   <span data-ttu-id="4dfc0-126">Rendimiento crítico</span><span class="sxs-lookup"><span data-stu-id="4dfc0-126">Performance critical</span></span>  
  
-   <span data-ttu-id="4dfc0-127">Con expiración en breve/Expirada</span><span class="sxs-lookup"><span data-stu-id="4dfc0-127">Expiring soon/Expired</span></span>  
  
-   <span data-ttu-id="4dfc0-128">Suscripción no inicializada</span><span class="sxs-lookup"><span data-stu-id="4dfc0-128">Uninitialized subscription</span></span>  
  
-   <span data-ttu-id="4dfc0-129">Reintentando comando con errores</span><span class="sxs-lookup"><span data-stu-id="4dfc0-129">Retrying failed command</span></span>  
  
-   <span data-ttu-id="4dfc0-130">No está en ejecución</span><span class="sxs-lookup"><span data-stu-id="4dfc0-130">Not Running</span></span>  
  
-   <span data-ttu-id="4dfc0-131">En ejecución</span><span class="sxs-lookup"><span data-stu-id="4dfc0-131">Running</span></span>  
  
 <span data-ttu-id="4dfc0-132">El criterio de clasificación también determina qué valor se muestra si una misma suscripción presenta varios estados.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-132">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="4dfc0-133">Por ejemplo, si una suscripción tiene un error y expirará en breve, la columna **Estado** muestra **Error**.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-133">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="4dfc0-134">Los valores de estado **Rendimiento crítico**, **Con expiración en breve/Expirado**y **Suscripción no inicializada** son advertencias.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-134">The status values **Performance critical**, **Expiring soon/Expired**, and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="4dfc0-135">Cuando se muestra una advertencia, también aparece la columna **Estado** si un agente está ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-135">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="4dfc0-136">Por ejemplo, el estado podría ser **En ejecución, Rendimiento crítico**.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-136">For example, the status could be **Running, Performance critical**.</span></span>  
  
 <span data-ttu-id="4dfc0-137">Los valores de estado **Rendimiento crítico** y **Con expiración en breve/Expirado** se muestran únicamente si se establecen umbrales.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-137">The status values **Performance critical** and **Expiring soon/Expired** are displayed only if thresholds are set.</span></span> <span data-ttu-id="4dfc0-138">Para obtener información sobre la medición del rendimiento y el establecimiento de umbrales, vea [Supervisar el rendimiento con el Monitor de replicación](monitor/monitor-performance-with-replication-monitor.md) y [Establecer umbrales y advertencias en el Monitor de replicación](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="4dfc0-138">For information about performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="4dfc0-139">**Suscripción**</span><span class="sxs-lookup"><span data-stu-id="4dfc0-139">**Subscription**</span></span>  
 <span data-ttu-id="4dfc0-140">Muestra el nombre de cada suscripción, en el formato: *nombreDeSuscriptor: nombreDeBaseDeDatosDeSuscripción*.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-140">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="4dfc0-141">**Publicación**</span><span class="sxs-lookup"><span data-stu-id="4dfc0-141">**Publication**</span></span>  
 <span data-ttu-id="4dfc0-142">Muestra el nombre de la publicación con la que se sincroniza una suscripción, en el formato: *nombreDeBaseDeDatosDePublicación: nombreDePublicación*.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-142">The name of the publication with which a subscription synchronizes, in the form: *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="4dfc0-143">**Rendimiento**</span><span class="sxs-lookup"><span data-stu-id="4dfc0-143">**Performance**</span></span>  
 <span data-ttu-id="4dfc0-144">La clasificación del rendimiento para cada suscripción se basa en las medidas más recientes tomadas por el Monitor de replicación y no refleja el rendimiento histórico.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-144">The performance rating for each subscription is based on the most recent measurements taken by Replication Monitor and does not reflect historical performance.</span></span> <span data-ttu-id="4dfc0-145">El rendimiento se mide para suscripciones a publicaciones que tienen definidos umbrales de rendimiento; si una publicación no tiene umbrales de rendimiento definidos, esta columna muestra **No habilitado**.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-145">Performance is measured for subscriptions to publications that have performance thresholds defined; if performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="4dfc0-146">La clasificación de rendimiento tiene uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="4dfc0-146">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="4dfc0-147">Excelente</span><span class="sxs-lookup"><span data-stu-id="4dfc0-147">Excellent</span></span>  
  
-   <span data-ttu-id="4dfc0-148">Bueno</span><span class="sxs-lookup"><span data-stu-id="4dfc0-148">Good</span></span>  
  
-   <span data-ttu-id="4dfc0-149">Regular</span><span class="sxs-lookup"><span data-stu-id="4dfc0-149">Fair</span></span>  
  
-   <span data-ttu-id="4dfc0-150">Insuficiente</span><span class="sxs-lookup"><span data-stu-id="4dfc0-150">Poor</span></span>  
  
-   <span data-ttu-id="4dfc0-151">Crítico</span><span class="sxs-lookup"><span data-stu-id="4dfc0-151">Critical</span></span>  
  
 <span data-ttu-id="4dfc0-152">Si el rendimiento es crítico, se muestra **Rendimiento crítico** en la columna **Estado** .</span><span class="sxs-lookup"><span data-stu-id="4dfc0-152">If performance is critical, **Performance Critical** is displayed in the **Status** column.</span></span> <span data-ttu-id="4dfc0-153">Para obtener más información sobre cómo se definen las clasificaciones de rendimiento y cómo se establecen los umbrales de rendimiento, vea [Supervisar el rendimiento con el Monitor de replicación](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="4dfc0-153">For more information about how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="4dfc0-154">**Latency**</span><span class="sxs-lookup"><span data-stu-id="4dfc0-154">**Latency**</span></span>  
 <span data-ttu-id="4dfc0-155">Muestra el tiempo promedio que transcurre entre la confirmación de una transacción en el publicador y la confirmación de la transacción correspondiente en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-155">The average amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="4dfc0-156">La latencia que se muestra se basa en las mediciones más recientes realizadas por el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-156">The latency displayed is based on the most recent measurements taken by Replication Monitor.</span></span> <span data-ttu-id="4dfc0-157">Para obtener más información sobre cómo medir la latencia, vea [Medir la latencia y validar las conexiones de la replicación transaccional](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="4dfc0-157">For more information about measuring latency, see [Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
 <span data-ttu-id="4dfc0-158">**Última sincronización**</span><span class="sxs-lookup"><span data-stu-id="4dfc0-158">**Last Synchronization**</span></span>  
 <span data-ttu-id="4dfc0-159">Indica la hora en que se ejecutó por última vez el Agente de distribución.</span><span class="sxs-lookup"><span data-stu-id="4dfc0-159">The time when the Distribution Agent last ran.</span></span> <span data-ttu-id="4dfc0-160">Si la sincronización está en curso, se muestra **En curso** .</span><span class="sxs-lookup"><span data-stu-id="4dfc0-160">If synchronization is in progress, **In progress** is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dfc0-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4dfc0-161">See Also</span></span>  
 <span data-ttu-id="4dfc0-162">[Iniciar el Monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="4dfc0-162">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="4dfc0-163">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="4dfc0-163">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="4dfc0-164">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="4dfc0-164">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
