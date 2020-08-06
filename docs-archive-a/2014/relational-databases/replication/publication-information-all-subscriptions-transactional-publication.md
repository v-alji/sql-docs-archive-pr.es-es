---
title: Información de publicación, Todas las suscripciones (Publicación transaccional) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.allsubscriptions.tran.f1
ms.assetid: 7073350c-f667-4f70-88e9-152c9a1b08dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ccc34bbe0933f4558478bd1d8276898219016e24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669621"
---
# <a name="publication-information-all-subscriptions-transactional-publication"></a><span data-ttu-id="d3b7c-102">Información de publicación, Todas las suscripciones (Publicación transaccional)</span><span class="sxs-lookup"><span data-stu-id="d3b7c-102">Publication Information, All Subscriptions (Transactional Publication)</span></span>
  <span data-ttu-id="d3b7c-103">La pestaña **Todas las suscripciones** muestra información de todas las suscripciones a la publicación transaccional seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-103">The **All Subscriptions** tab displays information on all subscriptions to the selected transactional publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d3b7c-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="d3b7c-104">Options</span></span>  
 <span data-ttu-id="d3b7c-105">Para obtener información más detallada y las tareas de una suscripción, haga clic con el botón secundario en la fila de dicha suscripción y, a continuación, haga clic en una opción del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-105">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="d3b7c-106">Para cambiar la manera que la cuadrícula muestra los datos, haga clic con el botón secundario en la cuadrícula y, a continuación, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3b7c-106">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="d3b7c-107">**Ordenar**: ordene en una o más columnas en el cuadro de diálogo **Ordenar columnas** .</span><span class="sxs-lookup"><span data-stu-id="d3b7c-107">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="d3b7c-108">**Elegir columnas para mostrar**: seleccione las columnas que se mostrarán y el orden en el que se mostrarán en el cuadro de diálogo **Elegir columnas** .</span><span class="sxs-lookup"><span data-stu-id="d3b7c-108">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="d3b7c-109">**Filtro**: filtre filas en la cuadrícula basándose en los valores de columna en el cuadro de diálogo **Configuración del filtro** .</span><span class="sxs-lookup"><span data-stu-id="d3b7c-109">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="d3b7c-110">**Borrar filtro**: borre cualquier configuración de filtro para la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-110">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="d3b7c-111">La configuración del filtro es específica de cada cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-111">Filter settings are specific to each grid.</span></span> <span data-ttu-id="d3b7c-112">La selección y ordenación de las columnas se aplica a todas las cuadrículas del mismo tipo, como la cuadrícula de las publicaciones para cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-112">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="d3b7c-113">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="d3b7c-113">**Show**</span></span>  
 <span data-ttu-id="d3b7c-114">Solo para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-114">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="d3b7c-115">Seleccione los estados de la suscripción que se mostrarán para el tipo de suscripción seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-115">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="d3b7c-116">Por ejemplo, puede seleccionar mostrar solo aquellas suscripciones que tienen errores.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-116">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="d3b7c-117">**Estado**</span><span class="sxs-lookup"><span data-stu-id="d3b7c-117">**Status**</span></span>  
 <span data-ttu-id="d3b7c-118">Es el estado de cada suscripción, determinado por el estado del Agente de distribución o el Agente de registro del LOG (se muestra el estado de prioridad más alto; el estado también se puede determinar mediante el Agente de lectura de cola si se utilizan suscripciones de actualización en cola).</span><span class="sxs-lookup"><span data-stu-id="d3b7c-118">The status of each subscription, which is determined by the status of the Distribution Agent or the Log Reader Agent (the higher priority status is displayed; the status can also be determined by the Queue Reader Agent if queued updating subscriptions are used).</span></span>  
  
 <span data-ttu-id="d3b7c-119">De forma predeterminada, la cuadrícula que contiene la información de suscripción está ordenada por la columna **Estado** (y, a continuación, por la columna **Rendimiento** de las suscripciones con el mismo estado).</span><span class="sxs-lookup"><span data-stu-id="d3b7c-119">By default, the grid containing subscription information is sorted by the **Status** column (and then sorted by the **Performance** column for those subscriptions with the same status).</span></span> <span data-ttu-id="d3b7c-120">La siguiente lista muestra los valores de estado posibles y el criterio de ordenación de los valores (por ejemplo, los errores se muestran siempre en la parte superior de la cuadrícula).</span><span class="sxs-lookup"><span data-stu-id="d3b7c-120">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="d3b7c-121">Error</span><span class="sxs-lookup"><span data-stu-id="d3b7c-121">Error</span></span>  
  
-   <span data-ttu-id="d3b7c-122">Rendimiento crítico (solo para[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="d3b7c-122">Performance critical ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="d3b7c-123">Con expiración en breve/Expirado (solo para[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="d3b7c-123">Expiring soon/Expired ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="d3b7c-124">Suscripción no inicializada (solo para[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="d3b7c-124">Uninitialized subscription ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="d3b7c-125">Reintentando comando con errores</span><span class="sxs-lookup"><span data-stu-id="d3b7c-125">Retrying failed command</span></span>  
  
-   <span data-ttu-id="d3b7c-126">No está en ejecución</span><span class="sxs-lookup"><span data-stu-id="d3b7c-126">Not Running</span></span>  
  
-   <span data-ttu-id="d3b7c-127">En ejecución</span><span class="sxs-lookup"><span data-stu-id="d3b7c-127">Running</span></span>  
  
 <span data-ttu-id="d3b7c-128">El criterio de clasificación también determina qué valor se muestra si una misma suscripción presenta varios estados.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-128">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="d3b7c-129">Por ejemplo, si una suscripción tiene un error y expirará en breve, la columna **Estado** muestra **Error**.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-129">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="d3b7c-130">Los valores de estado **Rendimiento crítico**, **Con expiración en breve/Expirado**y **Suscripción no inicializada** son advertencias.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-130">The status values **Performance critical**, **Expiring soon/Expired**, and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="d3b7c-131">Cuando se muestra una advertencia, también aparece la columna **Estado** si un agente está ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-131">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="d3b7c-132">Por ejemplo, el estado podría ser **En ejecución, Rendimiento crítico**.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-132">For example, the status could be **Running, Performance critical**.</span></span>  
  
 <span data-ttu-id="d3b7c-133">Los valores de estado **Rendimiento crítico** y **Con expiración en breve/Expirado** se muestran únicamente si se establecen umbrales.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-133">The status values **Performance critical** and **Expiring soon/Expired** are displayed only if thresholds are set.</span></span> <span data-ttu-id="d3b7c-134">Para obtener información sobre la medición del rendimiento y el establecimiento de umbrales, vea [Supervisar el rendimiento con el Monitor de replicación](monitor/monitor-performance-with-replication-monitor.md) y [Establecer umbrales y advertencias en el Monitor de replicación](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="d3b7c-134">For information on performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="d3b7c-135">**Suscripción**</span><span class="sxs-lookup"><span data-stu-id="d3b7c-135">**Subscription**</span></span>  
 <span data-ttu-id="d3b7c-136">Muestra el nombre de cada suscripción, en el formato: *nombreDeSuscriptor: nombreDeBaseDeDatosDeSuscripción*.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-136">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="d3b7c-137">**Rendimiento**</span><span class="sxs-lookup"><span data-stu-id="d3b7c-137">**Performance**</span></span>  
 <span data-ttu-id="d3b7c-138">Solo para[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-138">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="d3b7c-139">La clasificación del rendimiento para cada suscripción se basa en las medidas más recientes tomadas por el Monitor de replicación y no refleja el rendimiento histórico.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-139">The performance rating for each subscription is based on the most recent measurements taken by Replication Monitor and does not reflect historical performance.</span></span> <span data-ttu-id="d3b7c-140">El rendimiento se mide para suscripciones a publicaciones que tienen definidos umbrales de rendimiento; si una publicación no tiene umbrales de rendimiento definidos, esta columna muestra **No habilitado**.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-140">Performance is measured for subscriptions to publications that have performance thresholds defined; if performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="d3b7c-141">La clasificación de rendimiento tiene uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3b7c-141">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="d3b7c-142">Excelente</span><span class="sxs-lookup"><span data-stu-id="d3b7c-142">Excellent</span></span>  
  
-   <span data-ttu-id="d3b7c-143">Bueno</span><span class="sxs-lookup"><span data-stu-id="d3b7c-143">Good</span></span>  
  
-   <span data-ttu-id="d3b7c-144">Aceptable</span><span class="sxs-lookup"><span data-stu-id="d3b7c-144">Fair</span></span>  
  
-   <span data-ttu-id="d3b7c-145">Insuficiente</span><span class="sxs-lookup"><span data-stu-id="d3b7c-145">Poor</span></span>  
  
-   <span data-ttu-id="d3b7c-146">Crítica</span><span class="sxs-lookup"><span data-stu-id="d3b7c-146">Critical</span></span>  
  
 <span data-ttu-id="d3b7c-147">Si el rendimiento es crítico, se muestra **Rendimiento crítico** en la columna **Estado** .</span><span class="sxs-lookup"><span data-stu-id="d3b7c-147">If performance is critical, **Performance Critical** is displayed in the **Status** column.</span></span> <span data-ttu-id="d3b7c-148">Para obtener más información sobre cómo se definen las clasificaciones de rendimiento y cómo se establecen los umbrales de rendimiento, vea [Supervisar el rendimiento con el Monitor de replicación](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="d3b7c-148">For more information on how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="d3b7c-149">**Latency**</span><span class="sxs-lookup"><span data-stu-id="d3b7c-149">**Latency**</span></span>  
 <span data-ttu-id="d3b7c-150">Solo para[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-150">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="d3b7c-151">Muestra el tiempo promedio que transcurre entre la confirmación de una transacción en el publicador y la confirmación de la transacción correspondiente en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-151">The average amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="d3b7c-152">La latencia que se muestra se basa en las mediciones más recientes realizadas por el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-152">The latency displayed is based on the most recent measurements taken by Replication Monitor.</span></span> <span data-ttu-id="d3b7c-153">Para obtener más información sobre cómo medir la latencia, vea [Medir la latencia y validar las conexiones de la replicación transaccional](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="d3b7c-153">For more information about measuring latency, see [Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3b7c-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3b7c-154">See Also</span></span>  
 <span data-ttu-id="d3b7c-155">[Iniciar el monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d3b7c-155">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="d3b7c-156">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d3b7c-156">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="d3b7c-157">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="d3b7c-157">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
