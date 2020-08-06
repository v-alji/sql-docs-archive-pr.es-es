---
title: Establecer umbrales y advertencias en el Monitor de replicación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server replication]
- Merge Agent, thresholds and warnings
- Distribution Agent, thresholds and warnings
- thresholds [SQL Server replication]
- Replication Monitor, thresholds and warnings
- monitoring performance [SQL Server replication], thresholds and warnings
ms.assetid: 3a409c2c-b77e-4001-b81a-1dcd918618ec
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f34878a6398df34e55e6dd3783f2da736bee0959
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750726"
---
# <a name="set-thresholds-and-warnings-in-replication-monitor"></a><span data-ttu-id="89003-102">Establecer umbrales y advertencias en el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="89003-102">Set Thresholds and Warnings in Replication Monitor</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="89003-103">El [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] monitor de replicación muestra información de estado de las publicaciones y las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="89003-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor displays status information for publications and subscriptions.</span></span> <span data-ttu-id="89003-104">De forma predeterminada, en el Monitor de replicación solamente se muestran advertencias de suscripciones no inicializadas, pero puede habilitar advertencias para otras condiciones.</span><span class="sxs-lookup"><span data-stu-id="89003-104">By default, Replication Monitor displays warnings only for uninitialized subscriptions, but you can enable warnings for other conditions.</span></span> <span data-ttu-id="89003-105">Se recomienda habilitar las advertencias para la topología, con el fin de estar puntualmente informado sobre el estado y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="89003-105">It is recommended that you enable warnings for your topology, so that you are informed about status and performance in a timely manner.</span></span>  
  
 <span data-ttu-id="89003-106">Al habilitar una advertencia, debe especificar un umbral.</span><span class="sxs-lookup"><span data-stu-id="89003-106">When you enable a warning, you specify a threshold.</span></span> <span data-ttu-id="89003-107">Cuando se alcanza o se supera ese umbral, aparece la advertencia (a menos que haya un problema de mayor prioridad).</span><span class="sxs-lookup"><span data-stu-id="89003-107">When that threshold is met or exceeded, a warning is displayed (unless an issue with a higher priority needs to be displayed).</span></span> <span data-ttu-id="89003-108">Además de mostrar una advertencia en el Monitor de replicación, llegar a un umbral también puede desencadenar una alerta.</span><span class="sxs-lookup"><span data-stu-id="89003-108">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="89003-109">Se pueden habilitar advertencias para las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="89003-109">You can enable warnings for the following conditions:</span></span>  
  
-   <span data-ttu-id="89003-110">Expiración inminente de la suscripción</span><span class="sxs-lookup"><span data-stu-id="89003-110">Imminent subscription expiration</span></span>  
  
     <span data-ttu-id="89003-111">Se aplica a todos los tipos de replicación.</span><span class="sxs-lookup"><span data-stu-id="89003-111">This applies to all types of replication.</span></span> <span data-ttu-id="89003-112">Si se alcanza o se supera el umbral especificado, el estado de la suscripción se muestra como **Con expiración en breve/Expirada**.</span><span class="sxs-lookup"><span data-stu-id="89003-112">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired**.</span></span>  
  
-   <span data-ttu-id="89003-113">Si se supera la latencia especificada (el intervalo de tiempo que transcurre entre la confirmación de una transacción en el publicador y confirmación de la transacción correspondiente en el suscriptor).</span><span class="sxs-lookup"><span data-stu-id="89003-113">Exceeding the specified latency (the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber).</span></span>  
  
     <span data-ttu-id="89003-114">Esto se aplica a la replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="89003-114">This applies to transactional replication.</span></span> <span data-ttu-id="89003-115">Si se alcanza o se supera el umbral especificado, el estado de la suscripción se muestra como **Rendimiento crítico**.</span><span class="sxs-lookup"><span data-stu-id="89003-115">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical**.</span></span>  
  
-   <span data-ttu-id="89003-116">Si se supera el tiempo de sincronización especificado.</span><span class="sxs-lookup"><span data-stu-id="89003-116">Exceeding the specified synchronization time.</span></span>  
  
     <span data-ttu-id="89003-117">Esto se aplica a la replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="89003-117">This applies to merge replication.</span></span> <span data-ttu-id="89003-118">Si se alcanza o sobrepasa el umbral especificado, el estado se mostrará como **Mezcla de ejecución prolongada**.</span><span class="sxs-lookup"><span data-stu-id="89003-118">If the specified threshold is met or exceeded, the status is displayed as **Long-running merge**.</span></span> <span data-ttu-id="89003-119">Puede especificar diferentes umbrales para las conexiones de acceso telefónico y de red de área local (LAN).</span><span class="sxs-lookup"><span data-stu-id="89003-119">You can specify different thresholds for dialup and Local Area Network (LAN) connections.</span></span>  
  
-   <span data-ttu-id="89003-120">Si se produce un error en el procesamiento del número de filas especificado en un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="89003-120">Falling short of processing the specified number of rows in a given amount of time.</span></span>  
  
     <span data-ttu-id="89003-121">Esto se aplica a la replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="89003-121">This applies to merge replication.</span></span> <span data-ttu-id="89003-122">Si se alcanza o sobrepasa el umbral especificado, el estado se mostrará como **Rendimiento crítico**.</span><span class="sxs-lookup"><span data-stu-id="89003-122">If the specified threshold is met or exceeded, the status is displayed as **Performance critical**.</span></span> <span data-ttu-id="89003-123">Puede especificar diferentes umbrales para las conexiones de acceso telefónico y de LAN.</span><span class="sxs-lookup"><span data-stu-id="89003-123">You can specify different thresholds for dialup and LAN connections.</span></span>  
  
 <span data-ttu-id="89003-124">Para obtener más información sobre las advertencias **Rendimiento crítico** y **Mezcla de ejecución prolongada**, vea [Monitor Performance with Replication Monitor](monitor-performance-with-replication-monitor.md) (Rendimiento del Monitor con el Monitor de replicación).</span><span class="sxs-lookup"><span data-stu-id="89003-124">For more information on the warnings **Performance critical** and **Long-running merge**, see [Monitor Performance with Replication Monitor](monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="89003-125">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="89003-125">**In This Topic**</span></span>  
  
-   [<span data-ttu-id="89003-126">Establecer umbrales y advertencias para una publicación transaccional</span><span class="sxs-lookup"><span data-stu-id="89003-126">Set thresholds and warnings for a transactional publication</span></span>](#Transactional)  
  
-   [<span data-ttu-id="89003-127">Establecer umbrales y advertencias para una publicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="89003-127">Set thresholds and warnings for a merge publication</span></span>](#Merge)  
  
-   [<span data-ttu-id="89003-128">Establecer umbrales y advertencias para una publicación de instantánea</span><span class="sxs-lookup"><span data-stu-id="89003-128">Set thresholds and warnings for a snapshot publication</span></span>](#Snapshot)  
  
##  <a name="to-set-thresholds-and-warnings-for-a-transactional-publication"></a><a name="Transactional"></a><span data-ttu-id="89003-129">Para establecer umbrales y advertencias para una publicación transaccional</span><span class="sxs-lookup"><span data-stu-id="89003-129">To set thresholds and warnings for a transactional publication</span></span>  
  
1.  <span data-ttu-id="89003-130">Expanda un grupo de publicador en el panel izquierdo, expanda un publicador y, a continuación, haga clic en una publicación.</span><span class="sxs-lookup"><span data-stu-id="89003-130">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="89003-131">Haga clic en la pestaña **advertencias** . Para ver más información sobre las opciones de esta pestaña, haga clic en **ayuda** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="89003-131">Click the **Warnings** tab. To view more information about the options on this tab click **Help** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="89003-132">Para habilitar una advertencia, active la casilla apropiada: **Advertir si una suscripción expirará dentro del umbral** o **Advertir si la latencia supera el valor de umbral**.</span><span class="sxs-lookup"><span data-stu-id="89003-132">Enable a warning by selecting the appropriate check box: **Warn if a subscription will expire within the threshold** or **Warn if latency exceeds the threshold**.</span></span>  
  
4.  <span data-ttu-id="89003-133">En la columna **Umbral** , establezca un umbral para las advertencias.</span><span class="sxs-lookup"><span data-stu-id="89003-133">Set a threshold for the warnings in the **Threshold** column.</span></span> <span data-ttu-id="89003-134">Por ejemplo, si activó la casilla **Advertir si la latencia supera el valor de umbral** en el paso 3, puede seleccionar una latencia de **60 segundos** en la columna **Umbral** .</span><span class="sxs-lookup"><span data-stu-id="89003-134">For example, if you selected **Warn if latency exceeds the threshold** in step 3, you could select a latency of **60 seconds** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="89003-135">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="89003-135">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="89003-136">Para configurar una alerta para un umbral</span><span class="sxs-lookup"><span data-stu-id="89003-136">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="89003-137">Haga clic en **Configurar alertas**.</span><span class="sxs-lookup"><span data-stu-id="89003-137">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="89003-138">En el cuadro de diálogo **Configurar alertas de replicación** , seleccione una alerta y haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="89003-138">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="89003-139">Este cuadro de diálogo muestra alertas para todos los tipos de publicaciones, incluidas las alertas que no están relacionadas con los umbrales de supervisión.</span><span class="sxs-lookup"><span data-stu-id="89003-139">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span> <span data-ttu-id="89003-140">Para obtener más información, vea [Usar alertas para eventos del Agente de replicación](../agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="89003-140">For more information, see [Use Alerts for Replication Agent Events](../agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
3.  <span data-ttu-id="89003-141">Establezca las opciones en el cuadro de diálogo **Propiedades de la alerta \<AlertName>** :</span><span class="sxs-lookup"><span data-stu-id="89003-141">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="89003-142">En la página **General** , haga clic en **Habilitar**; especifique a qué base de datos desea que se aplique la alerta.</span><span class="sxs-lookup"><span data-stu-id="89003-142">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="89003-143">En la página **Respuesta** , especifique si desea que se envíe un mensaje de correo electrónico o que se ejecute un trabajo.</span><span class="sxs-lookup"><span data-stu-id="89003-143">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="89003-144">En la página **Opciones** , personalice el texto de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="89003-144">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="89003-145">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="89003-145">Click **Close**.</span></span>  
  
##  <a name="set-thresholds-and-warnings-for-a-merge-publication"></a><a name="Merge"></a><span data-ttu-id="89003-146">Establecer umbrales y advertencias para una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="89003-146">Set thresholds and warnings for a merge publication</span></span>  
  
1.  <span data-ttu-id="89003-147">Expanda un grupo de publicador en el panel izquierdo, expanda un publicador y, a continuación, haga clic en una publicación.</span><span class="sxs-lookup"><span data-stu-id="89003-147">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="89003-148">Haga clic en la pestaña **advertencias** . Para ver más información sobre las opciones de esta pestaña, haga clic en **ayuda** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="89003-148">Click the **Warnings** tab. To view more information about the options on this tab, click **Help** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="89003-149">Para habilitar una advertencia, active la casilla apropiada:</span><span class="sxs-lookup"><span data-stu-id="89003-149">Enable a warning by selecting the appropriate check box:</span></span>  
  
    -   <span data-ttu-id="89003-150">**Advertir si una suscripción expirará dentro del umbral**</span><span class="sxs-lookup"><span data-stu-id="89003-150">**Warn if a subscription will expire within the threshold**</span></span>  
  
    -   <span data-ttu-id="89003-151">**Advertir si la duración de una mezcla para las conexiones de acceso telefónico supera el valor de umbral**</span><span class="sxs-lookup"><span data-stu-id="89003-151">**Warn if a merge length for dialup connections exceeds the threshold**</span></span>  
  
    -   <span data-ttu-id="89003-152">**Advertir si la duración de una mezcla para las conexiones LAN supera el valor de umbral**</span><span class="sxs-lookup"><span data-stu-id="89003-152">**Warn if a merge length for LAN connections exceeds the threshold**</span></span>  
  
    -   <span data-ttu-id="89003-153">**Advertir si el número de filas mezcladas por segundo para las conexiones LAN es menor que el valor de umbral**</span><span class="sxs-lookup"><span data-stu-id="89003-153">**Warn if rows merged per second for LAN connections is less than the threshold**</span></span>  
  
    -   <span data-ttu-id="89003-154">**Advertir si el número de filas mezcladas por segundo para las conexiones de acceso telefónico es menor que el valor de umbral**</span><span class="sxs-lookup"><span data-stu-id="89003-154">**Warn if rows merged per second for dialup connections is less than the threshold**</span></span>  
  
4.  <span data-ttu-id="89003-155">En la columna **Umbral** , establezca umbrales para las advertencias.</span><span class="sxs-lookup"><span data-stu-id="89003-155">Set thresholds for the warnings in the **Threshold** column.</span></span> <span data-ttu-id="89003-156">Por ejemplo, si ha activado **Advertir si la duración de una mezcla para las conexiones de acceso telefónico supera el valor de umbral** en el paso 3, en la columna **Umbral** debe seleccionar un tiempo de **10 minutos** .</span><span class="sxs-lookup"><span data-stu-id="89003-156">For example, if you selected **Warn if a merge length for dialup connections exceeds the threshold** in step 3, you could select a time of **10 minutes** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="89003-157">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="89003-157">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="89003-158">Para configurar una alerta para un umbral</span><span class="sxs-lookup"><span data-stu-id="89003-158">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="89003-159">Haga clic en **Configurar alertas**.</span><span class="sxs-lookup"><span data-stu-id="89003-159">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="89003-160">En el cuadro de diálogo **Configurar alertas de replicación** , seleccione una alerta y haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="89003-160">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="89003-161">Este cuadro de diálogo muestra alertas para todos los tipos de publicaciones, incluidas las alertas que no están relacionadas con los umbrales de supervisión.</span><span class="sxs-lookup"><span data-stu-id="89003-161">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span>  
  
3.  <span data-ttu-id="89003-162">Establezca las opciones en el cuadro de diálogo **Propiedades de la alerta \<AlertName>** :</span><span class="sxs-lookup"><span data-stu-id="89003-162">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="89003-163">En la página **General** , haga clic en **Habilitar**; especifique a qué base de datos desea que se aplique la alerta.</span><span class="sxs-lookup"><span data-stu-id="89003-163">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="89003-164">En la página **Respuesta** , especifique si desea que se envíe un mensaje de correo electrónico o que se ejecute un trabajo.</span><span class="sxs-lookup"><span data-stu-id="89003-164">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="89003-165">En la página **Opciones** , personalice el texto de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="89003-165">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="89003-166">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="89003-166">Click **Close**.</span></span>  
  
##  <a name="set-thresholds-and-warnings-for-a-snapshot-publication"></a><a name="Snapshot"></a><span data-ttu-id="89003-167">Establecer umbrales y advertencias para una publicación de instantáneas</span><span class="sxs-lookup"><span data-stu-id="89003-167">Set thresholds and warnings for a snapshot publication</span></span>  
  
1.  <span data-ttu-id="89003-168">Expanda un grupo de publicador en el panel izquierdo, expanda un publicador y, a continuación, haga clic en una publicación.</span><span class="sxs-lookup"><span data-stu-id="89003-168">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="89003-169">Haga clic en la pestaña **advertencias** . Para ver más información acerca de las opciones de esta pestaña, haga clic en **ayuda** en el menú superior.</span><span class="sxs-lookup"><span data-stu-id="89003-169">Click the **Warnings** tab. To view more information about the options on this tab click **Help** on the top menu.</span></span>  
  
3.  <span data-ttu-id="89003-170">Para habilitar una advertencia, active la casilla **Advertir si una suscripción expirará dentro del umbral**.</span><span class="sxs-lookup"><span data-stu-id="89003-170">Enable a warning by selecting the check box **Warn if a subscription will expire within the threshold**.</span></span>  
  
4.  <span data-ttu-id="89003-171">En la columna **Umbral** , establezca un umbral para la advertencia.</span><span class="sxs-lookup"><span data-stu-id="89003-171">Set a threshold for the warning in the **Threshold** column.</span></span> <span data-ttu-id="89003-172">Por ejemplo, puede seleccionar un valor de **70%** en la columna **Umbral** .</span><span class="sxs-lookup"><span data-stu-id="89003-172">For example, you could select a value of **70%** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="89003-173">Haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="89003-173">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="89003-174">Para configurar una alerta para un umbral</span><span class="sxs-lookup"><span data-stu-id="89003-174">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="89003-175">Haga clic en **Configurar alertas**.</span><span class="sxs-lookup"><span data-stu-id="89003-175">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="89003-176">En el cuadro de diálogo **Configurar alertas de replicación** , seleccione una alerta y haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="89003-176">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="89003-177">Este cuadro de diálogo muestra alertas para todos los tipos de publicaciones, incluidas las alertas que no están relacionadas con los umbrales de supervisión.</span><span class="sxs-lookup"><span data-stu-id="89003-177">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span> <span data-ttu-id="89003-178">Para obtener más información, vea [Usar alertas para eventos del Agente de replicación](../agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="89003-178">For more information, see [Use Alerts for Replication Agent Events](../agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
3.  <span data-ttu-id="89003-179">Establezca las opciones en el cuadro de diálogo **Propiedades de la alerta \<AlertName>** :</span><span class="sxs-lookup"><span data-stu-id="89003-179">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="89003-180">En la página **General** , haga clic en **Habilitar**; especifique a qué base de datos desea que se aplique la alerta.</span><span class="sxs-lookup"><span data-stu-id="89003-180">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="89003-181">En la página **Respuesta** , especifique si desea que se envíe un mensaje de correo electrónico o que se ejecute un trabajo.</span><span class="sxs-lookup"><span data-stu-id="89003-181">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="89003-182">En la página **Opciones** , personalice el texto de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="89003-182">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="89003-183">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="89003-183">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89003-184">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89003-184">See Also</span></span>  
 [<span data-ttu-id="89003-185">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="89003-185">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
