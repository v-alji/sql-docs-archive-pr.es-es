---
title: Información de publicación, advertencias (publicación transaccional, SQL Server 2005 y versiones posteriores) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.tran.f1
ms.assetid: 4d4baf1d-d0a1-4d09-bec7-137811f43f09
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cac7ab0f712fe69d3736985921d70b0ce200d474
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746893"
---
# <a name="publication-information-warnings-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="80393-102">Información de publicación, Advertencias (Publicación transaccional, SQL Server 2005 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="80393-102">Publication Information, Warnings (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="80393-103">La pestaña **Advertencias** está disponible para los distribuidores que ejecutan [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="80393-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="80393-104">La pestaña **Advertencias** permite realizar las siguientes tareas para la publicación seleccionada:</span><span class="sxs-lookup"><span data-stu-id="80393-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="80393-105">Habilitar las advertencias para mostrarlas en el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="80393-105">Enable warnings to be displayed in Replication Monitor.</span></span>  
  
-   <span data-ttu-id="80393-106">Especificar umbrales asociados con las advertencias.</span><span class="sxs-lookup"><span data-stu-id="80393-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="80393-107">Definir alertas asociadas con advertencias.</span><span class="sxs-lookup"><span data-stu-id="80393-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="80393-108">Advertencias, umbrales y alertas</span><span class="sxs-lookup"><span data-stu-id="80393-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="80393-109">De forma predeterminada, el Monitor de replicación muestra advertencias de suscripciones no inicializadas: se muestra el estado **Suscripción no inicializada** como una advertencia en la columna **Estado** de las páginas que incluyen información de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="80393-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="80393-110">En publicaciones transaccionales, puede especificar si esas condiciones adicionales producen advertencias:</span><span class="sxs-lookup"><span data-stu-id="80393-110">For transactional publications, you can specify whether these additional conditions result in warnings:</span></span>  
  
-   <span data-ttu-id="80393-111">Expiración inminente de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="80393-111">Imminent subscription expiration.</span></span>  
  
     <span data-ttu-id="80393-112">Esta condición se corresponde con la opción **Advertir si una suscripción expirará dentro del umbral**.</span><span class="sxs-lookup"><span data-stu-id="80393-112">This corresponds to the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="80393-113">Si se alcanza o se supera el umbral especificado, se muestra el estado de la suscripción como **Con expiración en breve/Expirado** (a menos que tenga que mostrarse un problema con una prioridad superior).</span><span class="sxs-lookup"><span data-stu-id="80393-113">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="80393-114">Superar la latencia especificada.</span><span class="sxs-lookup"><span data-stu-id="80393-114">Exceeding the specified latency.</span></span> <span data-ttu-id="80393-115">Es el tiempo que transcurre entre la confirmación de una transacción en el publicador y la confirmación de la transacción correspondiente en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="80393-115">This is the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span>  
  
     <span data-ttu-id="80393-116">Esto se corresponde con la opción **Advertir si la latencia supera el valor de umbral**.</span><span class="sxs-lookup"><span data-stu-id="80393-116">This corresponds to the option **Warn if latency exceeds the threshold**.</span></span> <span data-ttu-id="80393-117">Si se alcanza o se supera el umbral especificado, se muestra el estado de la suscripción como **Rendimiento crítico** (a menos que tenga que mostrarse un problema con una prioridad superior).</span><span class="sxs-lookup"><span data-stu-id="80393-117">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical** (unless an issue with a higher priority needs to be displayed).</span></span> <span data-ttu-id="80393-118">El umbral también se utiliza para proporcionar una clasificación de rendimiento, que se muestra en la columna **Rendimiento** de las páginas que incluyen información de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="80393-118">The threshold is also used to provide a performance rating, which is displayed in the **Performance** column of pages that include subscription information.</span></span> <span data-ttu-id="80393-119">La clasificación de rendimiento tiene uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="80393-119">The performance rating is one of the following values:</span></span>  
  
    -   <span data-ttu-id="80393-120">Excelente</span><span class="sxs-lookup"><span data-stu-id="80393-120">Excellent</span></span>  
  
    -   <span data-ttu-id="80393-121">Bueno</span><span class="sxs-lookup"><span data-stu-id="80393-121">Good</span></span>  
  
    -   <span data-ttu-id="80393-122">Aceptable</span><span class="sxs-lookup"><span data-stu-id="80393-122">Fair</span></span>  
  
    -   <span data-ttu-id="80393-123">Insuficiente</span><span class="sxs-lookup"><span data-stu-id="80393-123">Poor</span></span>  
  
    -   <span data-ttu-id="80393-124">Crítico</span><span class="sxs-lookup"><span data-stu-id="80393-124">Critical</span></span>  
  
 <span data-ttu-id="80393-125">Cuando se habilita una advertencia, también se establece un umbral.</span><span class="sxs-lookup"><span data-stu-id="80393-125">When you enable a warning, you also set a threshold.</span></span> <span data-ttu-id="80393-126">Por ejemplo, si habilita la advertencia **Advertir si la latencia supera el valor de umbral**, seleccione el tiempo permitido entre que se confirma una transacción en el publicador y la transacción se confirma en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="80393-126">For example, if you enable the warning **Warn if latency exceeds the threshold**, select the amount of time allowable between a transaction being committed at the Publisher and the transaction being committed at the Subscriber.</span></span>  
  
 <span data-ttu-id="80393-127">Además de mostrar una advertencia en el Monitor de replicación, llegar a un umbral también puede desencadenar una alerta.</span><span class="sxs-lookup"><span data-stu-id="80393-127">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="80393-128">Para definir alertas, haga clic en **Configurar alertas** y proporcione información en el cuadro de diálogo **Configurar alertas de replicación** .</span><span class="sxs-lookup"><span data-stu-id="80393-128">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="80393-129">Opciones</span><span class="sxs-lookup"><span data-stu-id="80393-129">Options</span></span>  
 <span data-ttu-id="80393-130">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="80393-130">**Enabled**</span></span>  
 <span data-ttu-id="80393-131">Seleccione esta opción si desea habilitar una advertencia y especificar un umbral asociado.</span><span class="sxs-lookup"><span data-stu-id="80393-131">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="80393-132">**Advertencia**</span><span class="sxs-lookup"><span data-stu-id="80393-132">**Warning**</span></span>  
 <span data-ttu-id="80393-133">Descripción de la advertencia asociada al umbral.</span><span class="sxs-lookup"><span data-stu-id="80393-133">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="80393-134">**Umbral**</span><span class="sxs-lookup"><span data-stu-id="80393-134">**Threshold**</span></span>  
 <span data-ttu-id="80393-135">Permite especificar un valor para el umbral.</span><span class="sxs-lookup"><span data-stu-id="80393-135">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="80393-136">**Configurar alertas**</span><span class="sxs-lookup"><span data-stu-id="80393-136">**Configure Alerts**</span></span>  
 <span data-ttu-id="80393-137">Seleccione una fila en la cuadrícula **Advertencias** y haga clic en **Configurar alertas** para abrir el cuadro de diálogo **Configurar alertas de replicación** .</span><span class="sxs-lookup"><span data-stu-id="80393-137">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="80393-138">El cuadro de diálogo permite definir una alerta que se asociará al umbral y la advertencia seleccionados.</span><span class="sxs-lookup"><span data-stu-id="80393-138">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="80393-139">**Descartar cambios**</span><span class="sxs-lookup"><span data-stu-id="80393-139">**Discard Changes**</span></span>  
 <span data-ttu-id="80393-140">Haga clic para descartar los cambios realizados en las advertencias y los umbrales.</span><span class="sxs-lookup"><span data-stu-id="80393-140">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80393-141"> Hacer clic en **Descartar cambios** no afecta a las alertas definidas en el cuadro de diálogo **Configurar alertas de replicación** .</span><span class="sxs-lookup"><span data-stu-id="80393-141">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="80393-142">**Save Changes**</span><span class="sxs-lookup"><span data-stu-id="80393-142">**Save Changes**</span></span>  
 <span data-ttu-id="80393-143">Haga clic para guardar los cambios realizados en las advertencias y los umbrales.</span><span class="sxs-lookup"><span data-stu-id="80393-143">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80393-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="80393-144">See Also</span></span>  
 <span data-ttu-id="80393-145">[Iniciar el monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="80393-145">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="80393-146">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="80393-146">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="80393-147">[Supervisar el rendimiento con el monitor de replicación](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="80393-147">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="80393-148">[Monitoring Replication](monitoring-replication.md)  (Supervisar la replicación)</span><span class="sxs-lookup"><span data-stu-id="80393-148">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="80393-149">Establecer umbrales y advertencias en el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="80393-149">Set Thresholds and Warnings in Replication Monitor</span></span>](monitor/set-thresholds-and-warnings-in-replication-monitor.md)  
  
  
