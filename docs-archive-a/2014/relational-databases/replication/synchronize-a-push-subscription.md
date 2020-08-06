---
title: Sincronizar una suscripción de inserción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], push subscriptions
- subscriptions [SQL Server replication], push
- push subscriptions [SQL Server replication], synchronizing
ms.assetid: 0cfa7ae5-91d3-4a4f-9edf-a852d45783b5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fb2f7bd961748272d6cd67e3412b09d9370a6f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746237"
---
# <a name="synchronize-a-push-subscription"></a><span data-ttu-id="9c4ea-102">Sincronizar una suscripción de inserción</span><span class="sxs-lookup"><span data-stu-id="9c4ea-102">Synchronize a Push Subscription</span></span>
  <span data-ttu-id="9c4ea-103">En este tema se describe cómo sincronizar una suscripción de inserción en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [agentes de replicación](agents/replication-agents-overview.md)o Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="9c4ea-103">This topic describes how to synchronize a push subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [replication agents](agents/replication-agents-overview.md), or Replication Management Objects (RMO).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9c4ea-104">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c4ea-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="9c4ea-105">El Agente de distribución (para las instantáneas y la replicación transaccional) o el Agente de mezcla (para la replicación de mezcla) sincronizan las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-105">Subscriptions are synchronized by the Distribution Agent (for snapshot and transactional replication) or the Merge Agent (for merge replication).</span></span> <span data-ttu-id="9c4ea-106">Los agentes pueden ejecutarse continuamente, a petición o según una programación.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-106">Agents can run continuously, run on demand, or run on a schedule.</span></span> <span data-ttu-id="9c4ea-107">Para más información sobre la configuración de las programaciones de sincronización, vea [Especificar programaciones de sincronización](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="9c4ea-107">For more information about specifying synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="9c4ea-108">Sincronice una suscripción a petición de las carpetas **Publicaciones locales** y **Suscripciones locales** de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y la pestaña **Todas las suscripciones** del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-108">Synchronize a subscription on demand from the **Local Publications** and **Local Subscriptions** folders in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and the **All Subscriptions** tab in Replication Monitor.</span></span> <span data-ttu-id="9c4ea-109">Las suscripciones a publicaciones de Oracle no se pueden sincronizar a petición desde el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-109">Subscriptions to Oracle publications cannot be synchronized on demand from the Subscriber.</span></span> <span data-ttu-id="9c4ea-110">Para información sobre cómo iniciar el Monitor de replicación, vea [Iniciar el Monitor de replicación](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="9c4ea-110">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-management-studio-at-the-publisher"></a><span data-ttu-id="9c4ea-111">Para sincronizar una suscripción de inserción a petición en Management Studio (en el publicador)</span><span class="sxs-lookup"><span data-stu-id="9c4ea-111">To synchronize a push subscription on demand in Management Studio (at the Publisher)</span></span>  
  
1.  <span data-ttu-id="9c4ea-112">Conéctese al publicador en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]y luego expanda el nodo del servidor.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-112">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="9c4ea-113">Expanda la carpeta **Replicación** y, a continuación, expanda la carpeta **Publicaciones locales** .</span><span class="sxs-lookup"><span data-stu-id="9c4ea-113">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="9c4ea-114">Expanda la publicación en la que desea sincronizar las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-114">Expand the publication for which you want to synchronize subscriptions.</span></span>  
  
4.  <span data-ttu-id="9c4ea-115">Haga clic con el botón derecho en la suscripción que desea sincronizar y, a continuación, haga clic en **Ver estado de sincronización**.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-115">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
5.  <span data-ttu-id="9c4ea-116">En el cuadro de diálogo **Ver estado de sincronización - \<Subscriber>:\<SubscriptionDatabase>** haga clic en **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-116">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="9c4ea-117">Cuando se completa la sincronización, se muestra el mensaje **Sincronización completada**.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-117">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
6.  <span data-ttu-id="9c4ea-118">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-118">Click **Close**.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-management-studio-at-the-subscriber"></a><span data-ttu-id="9c4ea-119">Para sincronizar una suscripción de inserción a petición en Management Studio (en el suscriptor)</span><span class="sxs-lookup"><span data-stu-id="9c4ea-119">To synchronize a push subscription on demand in Management Studio (at the Subscriber)</span></span>  
  
1.  <span data-ttu-id="9c4ea-120">Conéctese al suscriptor en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]y expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-120">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="9c4ea-121">Expanda la carpeta **Replicación** y, a continuación, la carpeta **Suscripciones locales**.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="9c4ea-122">Haga clic con el botón derecho en la suscripción que desea sincronizar y, a continuación, haga clic en **Ver estado de sincronización**.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-122">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="9c4ea-123">Se muestra un mensaje acerca del establecimiento de una conexión con el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-123">A message is displayed about establishing a connection to the Distributor.</span></span> <span data-ttu-id="9c4ea-124">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-124">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="9c4ea-125">En el cuadro de diálogo **Ver estado de sincronización - \<Subscriber>:\<SubscriptionDatabase>** haga clic en **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-125">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="9c4ea-126">Cuando se completa la sincronización, se muestra el mensaje **Sincronización completada**.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-126">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
6.  <span data-ttu-id="9c4ea-127">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-127">Click **Close**.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-replication-monitor"></a><span data-ttu-id="9c4ea-128">Para sincronizar una suscripción de inserción a petición en el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="9c4ea-128">To synchronize a push subscription on demand in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="9c4ea-129">En el Monitor de replicación, expanda un grupo de publicador en el panel izquierdo, expanda un publicador y, a continuación, haga clic en una publicación.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-129">In Replication Monitor, expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="9c4ea-130">Haga clic en la pestaña **Todas las suscripciones** .</span><span class="sxs-lookup"><span data-stu-id="9c4ea-130">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="9c4ea-131">Haga clic con el botón secundario en la suscripción que desea sincronizar y, a continuación, haga clic en **Iniciar sincronización**.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-131">Right-click the subscription you want to synchronize, and then click **Start Synchronizing**.</span></span>  
  
4.  <span data-ttu-id="9c4ea-132">Para ver el progreso de la sincronización, haga clic con el botón secundario en la suscripción y, a continuación, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-132">To view synchronization progress, right-click the subscription, and then click **View Details**.</span></span>  
  
##  <a name="using-replication-agents"></a><a name="ReplProg"></a> <span data-ttu-id="9c4ea-133">Usar agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="9c4ea-133">Using Replication Agents</span></span>  
 <span data-ttu-id="9c4ea-134">Se pueden sincronizar las suscripciones de inserción mediante programación y a petición invocando el archivo ejecutable de agente de replicación adecuado del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-134">Push subscriptions can be synchronized programmatically and on-demand by invoking the appropriate replication agent executable file from the command prompt.</span></span> <span data-ttu-id="9c4ea-135">El archivo ejecutable de agente de replicación que se invoca dependerá del tipo de publicación a la que pertenece la suscripción de inserción.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-135">The replication agent executable file that is invoked will depend on the type of publication to which the push subscription belongs.</span></span>  
  
#### <a name="to-start-the-distribution-agent-to-synchronize-a-push-subscription-to-a-transactional-publication"></a><span data-ttu-id="9c4ea-136">Para iniciar el Agente de distribución para sincronizar una suscripción de inserción con una publicación transaccional</span><span class="sxs-lookup"><span data-stu-id="9c4ea-136">To start the Distribution Agent to synchronize a push subscription to a transactional publication</span></span>  
  
1.  <span data-ttu-id="9c4ea-137">Desde el símbolo del sistema o en un archivo por lotes, ejecute **distrib.exe**.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-137">From the command prompt or in a batch file at the Distributor, execute **distrib.exe**.</span></span> <span data-ttu-id="9c4ea-138">Especifique los argumentos de la línea de comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c4ea-138">Specify the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="9c4ea-139">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-139">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="9c4ea-140">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-140">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="9c4ea-141">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-141">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="9c4ea-142">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-142">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="9c4ea-143">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-143">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="9c4ea-144">**-SubscriptionType = 0**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-144">**-SubscriptionType = 0**</span></span>  
  
     <span data-ttu-id="9c4ea-145">Si está usando la autenticación de SQL Server, también debe especificar los argumentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c4ea-145">If you are using SQL Server Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="9c4ea-146">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-146">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="9c4ea-147">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-147">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="9c4ea-148">**-DistributorSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-148">**-DistributorSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="9c4ea-149">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-149">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="9c4ea-150">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-150">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="9c4ea-151">**-PublisherSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-151">**-PublisherSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="9c4ea-152">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-152">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="9c4ea-153">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-153">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="9c4ea-154">**-SubscriberSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-154">**-SubscriberSecurityMode = 0**</span></span>  
  
        > [!IMPORTANT]  
        >  [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
#### <a name="to-start-the-merge-agent-to-synchronize-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="9c4ea-155">Para iniciar el Agente de mezcla para sincronizar una suscripción de inserción con una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="9c4ea-155">To start the Merge Agent to synchronize a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="9c4ea-156">Desde el símbolo del sistema o en un archivo por lotes, ejecute **replmerg.exe**.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-156">From the command prompt or in a batch file at the Distributor, execute **replmerg.exe**.</span></span> <span data-ttu-id="9c4ea-157">Especifique los argumentos de la línea de comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c4ea-157">Specify the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="9c4ea-158">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-158">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="9c4ea-159">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-159">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="9c4ea-160">**-Publication**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-160">**-Publication**</span></span>  
  
    -   <span data-ttu-id="9c4ea-161">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-161">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="9c4ea-162">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-162">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="9c4ea-163">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-163">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="9c4ea-164">**-SubscriptionType = 0**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-164">**-SubscriptionType = 0**</span></span>  
  
     <span data-ttu-id="9c4ea-165">Si está usando la autenticación de SQL Server, también debe especificar los argumentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c4ea-165">If you are using SQL Server Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="9c4ea-166">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-166">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="9c4ea-167">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-167">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="9c4ea-168">**-DistributorSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-168">**-DistributorSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="9c4ea-169">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-169">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="9c4ea-170">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-170">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="9c4ea-171">**-PublisherSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-171">**-PublisherSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="9c4ea-172">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-172">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="9c4ea-173">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-173">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="9c4ea-174">**-SubscriberSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="9c4ea-174">**-SubscriberSecurityMode = 0**</span></span>  
  
        > [!IMPORTANT]  
        >  [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
###  <a name="examples-replication-agents"></a><a name="TsqlExample"></a> <span data-ttu-id="9c4ea-175">Ejemplos (agentes de replicación)</span><span class="sxs-lookup"><span data-stu-id="9c4ea-175">Examples (Replication Agents)</span></span>  
 <span data-ttu-id="9c4ea-176">El ejemplo siguiente inicia el Agente de distribución para sincronizar una suscripción de inserción.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-176">The following example starts the Distribution Agent to synchronize a push subscription.</span></span>  
  
 
```
REM -- Declare the variables.  
SET Publisher=%instancename%  
SET Subscriber=%instancename%  
SET PublicationDB=AdventureWorks2012  
SET SubscriptionDB=AdventureWorks2012Replica   
SET Publication=AdvWorksProductsTran  
  
REM -- Start the Distribution Agent with four subscription streams.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\DISTRIB.EXE" -Subscriber %Subscriber%   
-SubscriberDB %SubscriptionDB% -SubscriberSecurityMode 1 -Publication %Publication%   
-Publisher %Publisher% -PublisherDB %PublicationDB% -Distributor %Publisher%   
-DistributorSecurityMode 1 -Continuous -SubscriptionType 0 -SubscriptionStreams 4
```
  
 <span data-ttu-id="9c4ea-177">El ejemplo siguiente inicia el Agente de mezcla para sincronizar una suscripción de inserción.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-177">The following example starts the Merge Agent to synchronize a push subscription.</span></span>  

```
REM -- Declare the variables.  
SET Publisher=%instancename%  
SET Subscriber=%instancename%  
SET PublicationDB=AdventureWorks2012  
SET SubscriptionDB=AdventureWorks2012Replica   
SET Publication=AdvWorksSalesOrdersMerge  
  
REM -- Start the Merge Agent.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE"  -Publisher %Publisher%   
-Subscriber  %Subscriber%  -Distributor %Publisher% -PublisherDB  %PublicationDB%   
-SubscriberDB %SubscriptionDB% -Publication %Publication% -PublisherSecurityMode 1   
-OutputVerboseLevel 3  -Output -SubscriberSecurityMode 1  -SubscriptionType 0   
-DistributorSecurityMode 1
```
  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="9c4ea-178">Uso de Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="9c4ea-178">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="9c4ea-179">Puede sincronizar suscripciones de inserción mediante programación utilizando Replication Management Objects (RMO) y el acceso de código administrado a las funcionalidades del agente de replicación.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-179">You can synchronize push subscriptions programmatically by using Replication Management Objects (RMO) and managed code access to replication agent functionalities.</span></span> <span data-ttu-id="9c4ea-180">Las clases que se usan para crear una suscripción de inserción dependen del tipo de publicación al que pertenece la suscripción.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-180">The classes that you use to synchronize a push subscription depend on the type of publication to which the subscription belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9c4ea-181">Si desea iniciar una sincronización que se ejecute de forma autónoma sin afectar a la aplicación, inicie el agente asincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-181">If you want to start a synchronization that runs autonomously without affecting your application, start the agent asynchronously.</span></span> <span data-ttu-id="9c4ea-182">Sin embargo, si desea supervisar el resultado de la sincronización y recibir las devoluciones de llamada del agente durante el proceso de sincronización (por ejemplo, si desea mostrar una barra de progreso), debe iniciar el agente sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-182">However, if you want to monitor the outcome of the synchronization and receive callbacks from the agent during the synchronization process (for example, if you want to display a progress bar), you should start the agent synchronously.</span></span> <span data-ttu-id="9c4ea-183">Para los suscriptores de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)], debe iniciar el agente sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-183">For [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers, you must start the agent synchronously.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="9c4ea-184">Para sincronizar una suscripción de inserción a una publicación transaccional o de instantáneas</span><span class="sxs-lookup"><span data-stu-id="9c4ea-184">To synchronize a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="9c4ea-185">Cree una conexión al distribuidor mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="9c4ea-185">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="9c4ea-186">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.TransSubscription> y establezca las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c4ea-186">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class and set the following properties:</span></span>  
  
    -   <span data-ttu-id="9c4ea-187">El nombre de la base de datos de publicación para <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-187">The publication database name for <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="9c4ea-188">El nombre de la publicación a la que pertenece la suscripción para <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-188">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="9c4ea-189">El nombre de la base de datos de suscripciones para <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-189">The name of the subscription database for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="9c4ea-190">El nombre del Suscriptor para <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-190">The name of the Subscriber for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span></span>  
  
    -   <span data-ttu-id="9c4ea-191">La conexión creada en el paso 1 para <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-191">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="9c4ea-192">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obtener las propiedades de suscripción restantes.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-192">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="9c4ea-193">Si este método devuelve `false`, compruebe que la suscripción existe.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-193">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="9c4ea-194">Inicie el Agente de distribución en el Distribuidor de una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c4ea-194">Start the Distribution Agent at the Distributor in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="9c4ea-195">Llame al método <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizeWithJob%2A> en la instancia de <xref:Microsoft.SqlServer.Replication.TransSubscription> del paso 2.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-195">Call the <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.TransSubscription> from step 2.</span></span> <span data-ttu-id="9c4ea-196">Este método inicia el Agente de distribución de forma asincrónica y controla inmediatamente las devoluciones a la aplicación mientras se está ejecutando el trabajo del agente.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-196">This method starts the Distribution Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="9c4ea-197">No puede llamar a este método si la suscripción se creó con un valor `false` para <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-197">You cannot call this method if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span></span>  
  
    -   <span data-ttu-id="9c4ea-198">Obtenga una instancia de la clase <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> de la propiedad <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizationAgent%2A> y llame al método <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-198">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="9c4ea-199">Este método inicia el agente sincrónicamente y controla el resto con el trabajo del agente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-199">This method starts the agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="9c4ea-200">Durante la ejecución sincrónica, puede administrar el evento <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> mientras el agente se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-200">During synchronous execution you can handle the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="9c4ea-201">Para sincronizar una suscripción de inserción con una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="9c4ea-201">To synchronize a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="9c4ea-202">Cree una conexión al distribuidor mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="9c4ea-202">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="9c4ea-203">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.MergeSubscription> y establezca las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c4ea-203">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="9c4ea-204">El nombre de la base de datos de publicación para <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-204">The publication database name for <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="9c4ea-205">El nombre de la publicación a la que pertenece la suscripción para <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-205">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="9c4ea-206">El nombre de la base de datos de suscripciones para <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-206">The name of the subscription database for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="9c4ea-207">El nombre del Suscriptor para <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-207">The name of the Subscriber for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span></span>  
  
    -   <span data-ttu-id="9c4ea-208">La conexión creada en el paso 1 para <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-208">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="9c4ea-209">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obtener las propiedades de suscripción restantes.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-209">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="9c4ea-210">Si este método devuelve `false`, compruebe que la suscripción existe.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-210">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="9c4ea-211">Inicie el Agente de mezcla en el Distribuidor de una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c4ea-211">Start the Merge Agent at the Distributor in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="9c4ea-212">Llame al método <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizeWithJob%2A> en la instancia de <xref:Microsoft.SqlServer.Replication.MergeSubscription> del paso 2.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-212">Call the <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.MergeSubscription> from step 2.</span></span> <span data-ttu-id="9c4ea-213">Este método inicia el Agente de mezcla de forma asincrónica y controla inmediatamente las devoluciones a la aplicación mientras se está ejecutando el trabajo del agente.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-213">This method starts the Merge Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="9c4ea-214">No puede llamar a este método si la suscripción se creó con un valor `false` para <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-214">You cannot call this method if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span></span>  
  
    -   <span data-ttu-id="9c4ea-215">Obtenga una instancia de la clase <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> de la propiedad <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizationAgent%2A> y llame al método <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-215">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="9c4ea-216">Este método inicia el Agente de mezcla sincrónicamente y controla el resto con el trabajo del agente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-216">This method starts the Merge Agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="9c4ea-217">Durante la ejecución sincrónica, puede administrar el evento <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> mientras el agente se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-217">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="9c4ea-218">Ejemplos (RMO)</span><span class="sxs-lookup"><span data-stu-id="9c4ea-218">Examples (RMO)</span></span>  
 <span data-ttu-id="9c4ea-219">Este ejemplo sincroniza una suscripción de inserción con una publicación transaccional, en la que el agente se inicia forma asincrónica con el trabajo del agente.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-219">This example synchronizes a push subscription to a transactional publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPushSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpushsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPushSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpushsub_withjob)]  
  
 <span data-ttu-id="9c4ea-220">Este ejemplo sincroniza una suscripción de inserción con una publicación transaccional, en la que el agente se inicia sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-220">This example synchronizes a push subscription to a transactional publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpushsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpushsub)]  
  
 <span data-ttu-id="9c4ea-221">Este ejemplo sincroniza una suscripción de inserción con una publicación de combinación, en la que el agente se inicia forma asincrónica con el trabajo del agente.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-221">This example synchronizes a push subscription to a merge publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePushSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepushsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePushSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepushsub_withjob)]  
  
 <span data-ttu-id="9c4ea-222">Este ejemplo sincroniza una suscripción de inserción con una publicación de combinación, en la que el agente se inicia sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="9c4ea-222">This example synchronizes a push subscription to a merge publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepushsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepushsub)]  
  
## <a name="see-also"></a><span data-ttu-id="9c4ea-223">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c4ea-223">See Also</span></span>  
 <span data-ttu-id="9c4ea-224">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="9c4ea-224">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="9c4ea-225">[Sincronizar datos](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="9c4ea-225">[Synchronize Data](synchronize-data.md) </span></span>  
 [<span data-ttu-id="9c4ea-226">Procedimientos recomendados de seguridad de replicación</span><span class="sxs-lookup"><span data-stu-id="9c4ea-226">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
