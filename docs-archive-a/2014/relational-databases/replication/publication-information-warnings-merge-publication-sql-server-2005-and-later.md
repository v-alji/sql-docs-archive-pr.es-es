---
title: Información de publicación, advertencias (publicación de combinación, SQL Server 2005 y versiones posteriores) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.merge.f1
ms.assetid: 9bef3565-5f13-42ac-8723-ebe55b0c11e6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 75f58a4cd9bd84791acf7fd9d28147ef3bbd6232
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673650"
---
# <a name="publication-information-warnings-merge-publication-sql-server-2005-and-later"></a><span data-ttu-id="f8eb2-102">Información de publicación, Advertencias (Publicación de combinación, SQL Server 2005 y posterior)</span><span class="sxs-lookup"><span data-stu-id="f8eb2-102">Publication Information, Warnings (Merge Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="f8eb2-103">La pestaña **Advertencias** está disponible para los distribuidores que ejecutan [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="f8eb2-104">La pestaña **Advertencias** permite realizar las siguientes tareas para la publicación seleccionada:</span><span class="sxs-lookup"><span data-stu-id="f8eb2-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="f8eb2-105">Habilitar advertencias.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-105">Enable warnings.</span></span>  
  
-   <span data-ttu-id="f8eb2-106">Especificar umbrales asociados con las advertencias.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="f8eb2-107">Definir alertas asociadas con advertencias.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="f8eb2-108">Advertencias, umbrales y alertas</span><span class="sxs-lookup"><span data-stu-id="f8eb2-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="f8eb2-109">De forma predeterminada, el Monitor de replicación muestra advertencias de suscripciones no inicializadas: se muestra el estado **Suscripción no inicializada** como una advertencia en la columna **Estado** de las páginas que incluyen información de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="f8eb2-110">Para las publicaciones de combinación puede especificar si las siguientes condiciones adicionales generan advertencias:</span><span class="sxs-lookup"><span data-stu-id="f8eb2-110">For merge publications, you can specify whether these additional conditions result in warnings:</span></span>  
  
-   <span data-ttu-id="f8eb2-111">Expiración inminente de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-111">Imminent subscription expiration.</span></span>  
  
     <span data-ttu-id="f8eb2-112">Esta condición se corresponde con la opción **Advertir si una suscripción expirará dentro del umbral**.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-112">This corresponds to the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="f8eb2-113">Si se alcanza o se supera el umbral especificado, se muestra el estado de la suscripción como **Con expiración en breve/Expirado** (a menos que tenga que mostrarse un problema con una prioridad superior).</span><span class="sxs-lookup"><span data-stu-id="f8eb2-113">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="f8eb2-114">Si se supera el tiempo de sincronización especificado.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-114">Exceeding the specified synchronization time.</span></span>  
  
     <span data-ttu-id="f8eb2-115">Esta condición se corresponde con las opciones **Advertir si la duración de una mezcla para las conexiones de acceso telefónico supera el valor de umbral** y **Advertir si la duración de una mezcla para las conexiones LAN supera el valor de umbral**.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-115">This corresponds to the options **Warn if a merge length for dialup connections exceeds the threshold** and **Warn if a merge length for LAN connections exceeds the threshold**.</span></span> <span data-ttu-id="f8eb2-116">Es posible establecer el valor de ambos umbrales, pero solo se usará uno de ellos durante la sincronización.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-116">Both of these thresholds can be set, but only one is used during a given synchronization.</span></span> <span data-ttu-id="f8eb2-117">El Agente de mezcla aplicará el umbral apropiado en función del tipo de conexión.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-117">The Merge Agent applies the appropriate threshold based on the connection type.</span></span>  
  
     <span data-ttu-id="f8eb2-118">Si se alcanza o supera el umbral especificado, se muestra **Mezcla de ejecución prolongada** como estado de la suscripción (a menos que haya que mostrar un problema de prioridad más alta).</span><span class="sxs-lookup"><span data-stu-id="f8eb2-118">If the specified threshold is met or exceeded, the subscription status is displayed as **Long-running merge** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="f8eb2-119">Si se produce un error en el procesamiento del número de filas especificado en un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-119">Falling short of processing the specified number of rows in a given amount of time.</span></span>  
  
     <span data-ttu-id="f8eb2-120">Esta condición se corresponde con las opciones **Advertir si el número de filas mezcladas por segundo para las conexiones de acceso telefónico es menor que el valor de umbral** y **Advertir si la duración de una mezcla para las conexiones LAN supera el valor de umbral**.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-120">This corresponds to the options **Warn if rows merged per second for dialup connections is less than the threshold** and **Warn if a merge length for LAN connections exceeds the threshold**.</span></span> <span data-ttu-id="f8eb2-121">Es posible establecer el valor de ambos umbrales, pero solo se usará uno de ellos durante la sincronización.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-121">Both of these thresholds can be set, but only one is used during a given synchronization.</span></span> <span data-ttu-id="f8eb2-122">El Agente de mezcla aplicará el umbral apropiado en función del tipo de conexión.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-122">The Merge Agent applies the appropriate threshold based on the connection type.</span></span>  
  
     <span data-ttu-id="f8eb2-123">Si se alcanza o se supera el umbral especificado, se muestra el estado de la suscripción como **Rendimiento crítico** (a menos que tenga que mostrarse un problema con una prioridad superior).</span><span class="sxs-lookup"><span data-stu-id="f8eb2-123">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
 <span data-ttu-id="f8eb2-124">Cuando se habilita una advertencia, también se establece un umbral.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-124">When you enable a warning, you also set a threshold.</span></span> <span data-ttu-id="f8eb2-125">Por ejemplo, si se habilita la advertencia **Advertir si la duración de una mezcla para las conexiones LAN supera el valor de umbral**, se debe establecer el tiempo máximo permitido para una sincronización de mezcla.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-125">For example, if you enable the warning **Warn if a merge length for LAN connections exceeds the threshold**, set the maximum allowable length of time for a merge synchronization.</span></span>  
  
 <span data-ttu-id="f8eb2-126">Además de mostrar una advertencia en el Monitor de replicación, llegar a un umbral también puede desencadenar una alerta.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-126">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="f8eb2-127">Para definir alertas, haga clic en **Configurar alertas** y proporcione información en el cuadro de diálogo **Configurar alertas de replicación** .</span><span class="sxs-lookup"><span data-stu-id="f8eb2-127">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f8eb2-128">Opciones</span><span class="sxs-lookup"><span data-stu-id="f8eb2-128">Options</span></span>  
 <span data-ttu-id="f8eb2-129">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="f8eb2-129">**Enabled**</span></span>  
 <span data-ttu-id="f8eb2-130">Seleccione esta opción si desea habilitar una advertencia y especificar un umbral asociado.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-130">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="f8eb2-131">**Alerta**</span><span class="sxs-lookup"><span data-stu-id="f8eb2-131">**Alert**</span></span>  
 <span data-ttu-id="f8eb2-132">Seleccione esta opción para habilitar el valor de alerta para una advertencia determinada de replicación.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-132">Select to enable the alert setting for a given replication warning.</span></span>  
  
 <span data-ttu-id="f8eb2-133">**Advertencia**</span><span class="sxs-lookup"><span data-stu-id="f8eb2-133">**Warning**</span></span>  
 <span data-ttu-id="f8eb2-134">Descripción de la advertencia asociada al umbral.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-134">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="f8eb2-135">**Umbral**</span><span class="sxs-lookup"><span data-stu-id="f8eb2-135">**Threshold**</span></span>  
 <span data-ttu-id="f8eb2-136">Permite especificar un valor para el umbral.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-136">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="f8eb2-137">**Configurar alertas**</span><span class="sxs-lookup"><span data-stu-id="f8eb2-137">**Configure Alerts**</span></span>  
 <span data-ttu-id="f8eb2-138">Seleccione una fila en la cuadrícula **Advertencias** y haga clic en **Configurar alertas** para abrir el cuadro de diálogo **Configurar alertas de replicación** .</span><span class="sxs-lookup"><span data-stu-id="f8eb2-138">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="f8eb2-139">El cuadro de diálogo permite definir una alerta que se asociará al umbral y la advertencia seleccionados.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-139">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="f8eb2-140">**Descartar cambios**</span><span class="sxs-lookup"><span data-stu-id="f8eb2-140">**Discard Changes**</span></span>  
 <span data-ttu-id="f8eb2-141">Haga clic para descartar los cambios realizados en las advertencias y los umbrales.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-141">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f8eb2-142"> Hacer clic en **Descartar cambios** no afecta a las alertas definidas en el cuadro de diálogo **Configurar alertas de replicación** .</span><span class="sxs-lookup"><span data-stu-id="f8eb2-142">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="f8eb2-143">**Save Changes**</span><span class="sxs-lookup"><span data-stu-id="f8eb2-143">**Save Changes**</span></span>  
 <span data-ttu-id="f8eb2-144">Haga clic para guardar los cambios realizados en las advertencias y los umbrales.</span><span class="sxs-lookup"><span data-stu-id="f8eb2-144">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8eb2-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f8eb2-145">See Also</span></span>  
 <span data-ttu-id="f8eb2-146">[Iniciar el monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f8eb2-146">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="f8eb2-147">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f8eb2-147">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="f8eb2-148">[Supervisar el rendimiento con el monitor de replicación](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f8eb2-148">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="f8eb2-149">[Monitoring Replication](monitoring-replication.md)  (Supervisar la replicación)</span><span class="sxs-lookup"><span data-stu-id="f8eb2-149">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="f8eb2-150">Establecer umbrales y advertencias en el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="f8eb2-150">Set Thresholds and Warnings in Replication Monitor</span></span>](monitor/set-thresholds-and-warnings-in-replication-monitor.md)  
  
  
