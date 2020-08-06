---
title: Sincronización de una suscripción de extracción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- pull subscriptions [SQL Server replication], synchronizing
- synchronization [SQL Server replication], pull subscriptions
- subscriptions [SQL Server replication], pull
ms.assetid: 3ca24b23-fdc3-408e-8208-a2ace48fc8e3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 826622cd17862c0535e60c01baab756af2b2996b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673641"
---
# <a name="synchronize-a-pull-subscription"></a><span data-ttu-id="2abfb-102">Sincronización de una suscripción de extracción</span><span class="sxs-lookup"><span data-stu-id="2abfb-102">Synchronize a Pull Subscription</span></span>
  <span data-ttu-id="2abfb-103">En este tema se describe cómo sincronizar una suscripción de extracción en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [agentes de replicación](agents/replication-agents-overview.md) o Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="2abfb-103">This topic describes how to synchronize a pull subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [replication agents](agents/replication-agents-overview.md), or Replication Management Objects (RMO).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2abfb-104">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2abfb-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="2abfb-105">El Agente de distribución (para las instantáneas y la replicación transaccional) o el Agente de mezcla (para la replicación de mezcla) sincronizan las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="2abfb-105">Subscriptions are synchronized by the Distribution Agent (for snapshot and transactional replication) or the Merge Agent (for merge replication).</span></span> <span data-ttu-id="2abfb-106">Los agentes pueden ejecutarse continuamente, a petición o según una programación.</span><span class="sxs-lookup"><span data-stu-id="2abfb-106">Agents can run continuously, run on demand, or run on a schedule.</span></span> <span data-ttu-id="2abfb-107">Para más información sobre la configuración de las programaciones de sincronización, vea [Especificar programaciones de sincronización](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="2abfb-107">For more information about specifying synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="2abfb-108">Sincronice una suscripción a petición desde la carpeta **Suscripciones locales** de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2abfb-108">Synchronize a subscription on demand from the **Local Subscriptions** folder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-on-demand-in-management-studio"></a><span data-ttu-id="2abfb-109">Para sincronizar una suscripción de extracción a petición en Management Studio</span><span class="sxs-lookup"><span data-stu-id="2abfb-109">To synchronize a pull subscription on demand in Management Studio</span></span>  
  
1.  <span data-ttu-id="2abfb-110">Conéctese al suscriptor en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]y expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="2abfb-110">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="2abfb-111">Expanda la carpeta **Replicación** y, a continuación, la carpeta **Suscripciones locales**.</span><span class="sxs-lookup"><span data-stu-id="2abfb-111">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="2abfb-112">Haga clic con el botón derecho en la suscripción que desea sincronizar y, a continuación, haga clic en **Ver estado de sincronización**.</span><span class="sxs-lookup"><span data-stu-id="2abfb-112">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="2abfb-113">En el cuadro de diálogo **Ver estado de sincronización - \<Subscriber>:\<SubscriptionDatabase>** haga clic en **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="2abfb-113">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="2abfb-114">Cuando se completa la sincronización, se muestra el mensaje **Sincronización completada**.</span><span class="sxs-lookup"><span data-stu-id="2abfb-114">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
5.  <span data-ttu-id="2abfb-115">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2abfb-115">Click **Close**.</span></span>  
  
##  <a name="replication-agents"></a><a name="ReplProg"></a> <span data-ttu-id="2abfb-116">Agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="2abfb-116">Replication Agents</span></span>  
 <span data-ttu-id="2abfb-117">Se pueden sincronizar las suscripciones de extracción mediante programación y a petición invocando el archivo ejecutable del agente de replicación adecuado del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="2abfb-117">Pull subscriptions can be synchronized programmatically and on-demand by invoking the appropriate replication agent executable file from the command prompt.</span></span> <span data-ttu-id="2abfb-118">El archivo ejecutable de agente de replicación que se invoca dependerá del tipo de publicación a la que pertenece la suscripción de extracción.</span><span class="sxs-lookup"><span data-stu-id="2abfb-118">The replication agent executable file that is invoked will depend on the type of publication to which the pull subscription belongs.</span></span> <span data-ttu-id="2abfb-119">Para más información, consulte [Agentes de replicación](agents/replication-agents-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2abfb-119">For more information, see [Replication Agents](agents/replication-agents-overview.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2abfb-120">Los agentes de replicación se conectan al servidor local con las credenciales de autenticación de Windows del usuario que inició el agente desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="2abfb-120">Replication agents connect to the local server using the Windows Authentication credentials of the user who started the agent from the command prompt.</span></span> <span data-ttu-id="2abfb-121">También se usan estas credenciales de Windows al conectarse a los servidores remotos con la autenticación integrada de Windows.</span><span class="sxs-lookup"><span data-stu-id="2abfb-121">These Windows credentials are also used when connecting to remote servers using Windows Integrated Authentication.</span></span>  
  
#### <a name="to-start-the-distribution-agent-from-the-command-prompt-or-from-a-batch-file"></a><span data-ttu-id="2abfb-122">Para iniciar el agente de distribución desde el símbolo del sistema o desde un archivo por lotes</span><span class="sxs-lookup"><span data-stu-id="2abfb-122">To start the distribution agent from the command prompt or from a batch file</span></span>  
  
1.  <span data-ttu-id="2abfb-123">Desde el símbolo del sistema o en un archivo por lotes, inicie el [Agente de distribución de replicación](agents/replication-distribution-agent.md) ejecutando **distrib.exe** y especificando los argumentos de la línea de comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2abfb-123">From the command prompt or in a batch file, start the [Replication Distribution Agent](agents/replication-distribution-agent.md) by running **distrib.exe**, specifying the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="2abfb-124">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="2abfb-124">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="2abfb-125">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="2abfb-125">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="2abfb-126">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="2abfb-126">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="2abfb-127">**-DistributorSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="2abfb-127">**-DistributorSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="2abfb-128">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="2abfb-128">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="2abfb-129">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="2abfb-129">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="2abfb-130">**-SubscriberSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="2abfb-130">**-SubscriberSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="2abfb-131">**-SubscriptionType** = **1**</span><span class="sxs-lookup"><span data-stu-id="2abfb-131">**-SubscriptionType** = **1**</span></span>  
  
     <span data-ttu-id="2abfb-132">Si está usando la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], también debe especificar los argumentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2abfb-132">If you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="2abfb-133">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="2abfb-133">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="2abfb-134">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="2abfb-134">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="2abfb-135">**-DistributorSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="2abfb-135">**-DistributorSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="2abfb-136">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="2abfb-136">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="2abfb-137">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="2abfb-137">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="2abfb-138">**-PublisherSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="2abfb-138">**-PublisherSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="2abfb-139">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="2abfb-139">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="2abfb-140">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="2abfb-140">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="2abfb-141">**-SubscriberSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="2abfb-141">**-SubscriberSecurityMode** = **0**</span></span>  
  
#### <a name="to-start-the-merge-agent-from-the-command-prompt-or-from-a-batch-file"></a><span data-ttu-id="2abfb-142">Para iniciar el agente de mezcla desde el símbolo del sistema o desde un archivo por lotes</span><span class="sxs-lookup"><span data-stu-id="2abfb-142">To start the merge agent from the command prompt or from a batch file</span></span>  
  
1.  <span data-ttu-id="2abfb-143">Desde el símbolo del sistema o en un archivo por lotes, inicie el [Agente de mezcla de replicación](agents/replication-merge-agent.md) ejecutando **replmerg.exe** y especificando los argumentos de la línea de comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2abfb-143">From the command prompt or in a batch file, start the [Replication Merge Agent](agents/replication-merge-agent.md) by running **replmerg.exe**, specifying the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="2abfb-144">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="2abfb-144">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="2abfb-145">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="2abfb-145">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="2abfb-146">**-PublisherSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="2abfb-146">**-PublisherSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="2abfb-147">**-Publication**</span><span class="sxs-lookup"><span data-stu-id="2abfb-147">**-Publication**</span></span>  
  
    -   <span data-ttu-id="2abfb-148">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="2abfb-148">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="2abfb-149">**-DistributorSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="2abfb-149">**-DistributorSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="2abfb-150">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="2abfb-150">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="2abfb-151">**-SubscriberSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="2abfb-151">**-SubscriberSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="2abfb-152">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="2abfb-152">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="2abfb-153">**-SubscriptionType** = **1**</span><span class="sxs-lookup"><span data-stu-id="2abfb-153">**-SubscriptionType** = **1**</span></span>  
  
     <span data-ttu-id="2abfb-154">Si está usando la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], también debe especificar los argumentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2abfb-154">If you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="2abfb-155">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="2abfb-155">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="2abfb-156">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="2abfb-156">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="2abfb-157">**-DistributorSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="2abfb-157">**-DistributorSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="2abfb-158">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="2abfb-158">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="2abfb-159">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="2abfb-159">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="2abfb-160">**-PublisherSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="2abfb-160">**-PublisherSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="2abfb-161">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="2abfb-161">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="2abfb-162">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="2abfb-162">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="2abfb-163">**-SubscriberSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="2abfb-163">**-SubscriberSecurityMode** = **0**</span></span>  
  
###  <a name="examples-replication-agents"></a><a name="TsqlExample"></a> <span data-ttu-id="2abfb-164">Ejemplos (agentes de replicación)</span><span class="sxs-lookup"><span data-stu-id="2abfb-164">Examples (Replication Agents)</span></span>  
 <span data-ttu-id="2abfb-165">El ejemplo siguiente inicia el Agente de distribución para sincronizar una suscripción de extracción.</span><span class="sxs-lookup"><span data-stu-id="2abfb-165">The following example starts the Distribution Agent to synchronize a pull subscription.</span></span> <span data-ttu-id="2abfb-166">Todas las conexiones se realizan con la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="2abfb-166">All connections are made using Windows Authentication.</span></span>  
  
 [!code-sql[HowTo#bat_synctranpullsub_10](../../snippets/tsql/SQL15/replication/howto/tsql/synctranpullsub_10.bat)]  
  
 <span data-ttu-id="2abfb-167">El ejemplo siguiente inicia el Agente de mezcla para sincronizar una suscripción de extracción.</span><span class="sxs-lookup"><span data-stu-id="2abfb-167">The following example starts the Merge Agent to synchronize a pull subscription.</span></span> <span data-ttu-id="2abfb-168">Todas las conexiones se realizan con la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="2abfb-168">All connections are made using Windows Authentication.</span></span>  
  
 [!code-sql[HowTo#bat_syncmergepullsub_10](../../snippets/tsql/SQL15/replication/howto/tsql/syncmergepullsub_10.bat)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="2abfb-169">Uso de Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="2abfb-169">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="2abfb-170">Puede sincronizar suscripciones de extracción mediante programación con Replication Management Objects (RMO) y el acceso de código administrado a las funcionalidades del agente de replicación.</span><span class="sxs-lookup"><span data-stu-id="2abfb-170">You can synchronize pull subscriptions programmatically by using Replication Management Objects (RMO) and managed code access to replication agent functionalities.</span></span> <span data-ttu-id="2abfb-171">Las clases que se usan para crear una suscripción de extracción dependen del tipo de publicación al que pertenece la suscripción.</span><span class="sxs-lookup"><span data-stu-id="2abfb-171">The classes you use to synchronize a pull subscription depend on the type of publication to which the subscription belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2abfb-172">Si desea iniciar una sincronización que se ejecute de forma autónoma sin afectar a la aplicación, inicie el agente asincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="2abfb-172">If you want to start a synchronization that runs autonomously without affecting your application, start the agent asynchronously.</span></span> <span data-ttu-id="2abfb-173">Sin embargo, si desea supervisar el resultado de la sincronización y recibir las devoluciones de llamada del agente durante el proceso de sincronización (por ejemplo, para mostrar una barra de progreso), debe iniciar el agente sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="2abfb-173">However, if you want to monitor the outcome of the synchronization and receive callbacks from the agent during the synchronization process (for example, to display a progress bar), you should start the agent synchronously.</span></span> <span data-ttu-id="2abfb-174">Para los suscriptores de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)], debe iniciar el agente sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="2abfb-174">For [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers, you must start the agent synchronously.</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="2abfb-175">Para sincronizar una suscripción de extracción con una publicación transaccional o de instantáneas</span><span class="sxs-lookup"><span data-stu-id="2abfb-175">To synchronize a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="2abfb-176">Cree una conexión al suscriptor mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="2abfb-176">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="2abfb-177">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.TransPullSubscription> y establezca las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="2abfb-177">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="2abfb-178">El nombre de la base de datos de suscripciones para <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2abfb-178">The subscription database name for <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="2abfb-179">El nombre de la publicación a la que pertenece la suscripción para <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2abfb-179">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="2abfb-180">El nombre de la base de datos de publicación para <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2abfb-180">The name of the publication database for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="2abfb-181">El nombre del publicador para <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2abfb-181">The name of the Publisher for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span></span>  
  
    -   <span data-ttu-id="2abfb-182">La conexión creada en el paso 1 para <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="2abfb-182">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="2abfb-183">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obtener las propiedades de suscripción restantes.</span><span class="sxs-lookup"><span data-stu-id="2abfb-183">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="2abfb-184">Si este método devuelve `false`, compruebe que la suscripción existe.</span><span class="sxs-lookup"><span data-stu-id="2abfb-184">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="2abfb-185">Inicie el Agente de distribución en el suscriptor de una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="2abfb-185">Start the Distribution Agent at the Subscriber in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="2abfb-186">Llame al método <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizeWithJob%2A> en la instancia de <xref:Microsoft.SqlServer.Replication.TransPullSubscription> del paso 2.</span><span class="sxs-lookup"><span data-stu-id="2abfb-186">Call the <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.TransPullSubscription> from step 2.</span></span> <span data-ttu-id="2abfb-187">Este método inicia el Agente de distribución de forma asincrónica y controla inmediatamente las devoluciones a la aplicación mientras se está ejecutando el trabajo del agente.</span><span class="sxs-lookup"><span data-stu-id="2abfb-187">This method starts the Distribution Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="2abfb-188">No puede llamar a este método para suscriptores de [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] o si la suscripción se creó con un valor de `false` para <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (predeterminado).</span><span class="sxs-lookup"><span data-stu-id="2abfb-188">You cannot call this method for [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers or if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default).</span></span>  
  
    -   <span data-ttu-id="2abfb-189">Obtenga una instancia de la clase <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> de la propiedad <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizationAgent%2A> y llame al método <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A>.</span><span class="sxs-lookup"><span data-stu-id="2abfb-189">Get an instance of the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="2abfb-190">Este método inicia el agente sincrónicamente y controla el resto con el trabajo del agente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="2abfb-190">This method starts the agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="2abfb-191">Durante la ejecución sincrónica, puede administrar el evento <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> mientras el agente se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="2abfb-191">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2abfb-192">Si especificó un valor de `false` para <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (predeterminado) cuando creó la suscripción de extracción, también debe especificar <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Distributor%2A> , <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorSecurityMode%2A> y, opcionalmente, <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorLogin%2A> y <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorPassword%2A> porque los metadatos relacionados con el trabajo del agente para la suscripción no están disponibles en [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2abfb-192">If you specified a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default) when you created the pull subscription, you also need to specify <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Distributor%2A>, <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorSecurityMode%2A>, and optionally <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorLogin%2A> and <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorPassword%2A> because the agent job related metadata for the subscription is not available in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="2abfb-193">Para sincronizar una suscripción de extracción con una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="2abfb-193">To synchronize a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="2abfb-194">Cree una conexión al suscriptor mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="2abfb-194">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="2abfb-195">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.MergePullSubscription> y establezca las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="2abfb-195">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="2abfb-196">El nombre de la base de datos de suscripciones para <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2abfb-196">The subscription database name for <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="2abfb-197">El nombre de la publicación a la que pertenece la suscripción para <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2abfb-197">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="2abfb-198">El nombre de la base de datos publicada para <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2abfb-198">The name of the published database for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="2abfb-199">El nombre del publicador para <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span><span class="sxs-lookup"><span data-stu-id="2abfb-199">The name of the Publisher for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span></span>  
  
    -   <span data-ttu-id="2abfb-200">La conexión creada en el paso 1 para <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="2abfb-200">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="2abfb-201">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obtener las propiedades de suscripción restantes.</span><span class="sxs-lookup"><span data-stu-id="2abfb-201">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="2abfb-202">Si este método devuelve `false`, compruebe que la suscripción existe.</span><span class="sxs-lookup"><span data-stu-id="2abfb-202">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="2abfb-203">Inicie el Agente de mezcla en el suscriptor de una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="2abfb-203">Start the Merge Agent at the Subscriber in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="2abfb-204">Llame al método <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizeWithJob%2A> en la instancia de <xref:Microsoft.SqlServer.Replication.MergePullSubscription> del paso 2.</span><span class="sxs-lookup"><span data-stu-id="2abfb-204">Call the <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.MergePullSubscription> from step 2.</span></span> <span data-ttu-id="2abfb-205">Este método inicia el Agente de mezcla de forma asincrónica y controla inmediatamente las devoluciones a la aplicación mientras se está ejecutando el trabajo del agente.</span><span class="sxs-lookup"><span data-stu-id="2abfb-205">This method starts the Merge Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="2abfb-206">No puede llamar a este método para suscriptores de [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] o si la suscripción se creó con un valor de `false` para <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (predeterminado).</span><span class="sxs-lookup"><span data-stu-id="2abfb-206">You cannot call this method for [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers or if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default).</span></span>  
  
    -   <span data-ttu-id="2abfb-207">Obtenga una instancia de la clase <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> de la propiedad <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizationAgent%2A> y llame al método <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A>.</span><span class="sxs-lookup"><span data-stu-id="2abfb-207">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="2abfb-208">Este método inicia el Agente de mezcla sincrónicamente y controla el resto con el trabajo del agente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="2abfb-208">This method starts the Merge Agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="2abfb-209">Durante la ejecución sincrónica, puede administrar el evento <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> mientras el agente se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="2abfb-209">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2abfb-210">Si especificó un valor de `false` para <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (predeterminado) cuando creó la suscripción de extracción, también debe especificar <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Distributor%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorSecurityMode%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherSecurityMode%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.HostName%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.SubscriptionType%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.ExchangeType%2A> y, opcionalmente,, y <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorLogin%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorPassword%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherLogin%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherPassword%2A> porque los metadatos relacionados con el trabajo del agente para la suscripción no están disponibles en [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2abfb-210">If you specified a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default) when you created the pull subscription, you also need to specify <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Distributor%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorSecurityMode%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherSecurityMode%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.HostName%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.SubscriptionType%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.ExchangeType%2A>, and optionally <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorLogin%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorPassword%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherLogin%2A>, and <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherPassword%2A> because the agent job related metadata for the subscription is not available in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="2abfb-211">Ejemplos (RMO)</span><span class="sxs-lookup"><span data-stu-id="2abfb-211">Examples (RMO)</span></span>  
 <span data-ttu-id="2abfb-212">Este ejemplo sincroniza una suscripción de extracción con una publicación transaccional, en la que el agente se inicia de forma asincrónica con el trabajo del agente.</span><span class="sxs-lookup"><span data-stu-id="2abfb-212">This example synchronizes a pull subscription to a transactional publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPullSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpullsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPullSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpullsub_withjob)]  
  
 <span data-ttu-id="2abfb-213">Este ejemplo sincroniza una suscripción de extracción con una publicación transaccional, en la que el agente se inicia sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="2abfb-213">This example synchronizes a pull subscription to a transactional publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPullSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpullsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPullSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpullsub)]  
  
 <span data-ttu-id="2abfb-214">Este ejemplo sincroniza una suscripción de extracción con una publicación de combinación, en la que el agente se inicia de forma asincrónica con el trabajo del agente.</span><span class="sxs-lookup"><span data-stu-id="2abfb-214">This example synchronizes a pull subscription to a merge publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub_withjob)]  
  
 <span data-ttu-id="2abfb-215">Este ejemplo sincroniza una suscripción de extracción con una publicación de combinación, en la que el agente se inicia sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="2abfb-215">This example synchronizes a pull subscription to a merge publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub)]  
  
 <span data-ttu-id="2abfb-216">Este ejemplo sincroniza una suscripción de extracción con una publicación de combinación mediante la sincronización web.</span><span class="sxs-lookup"><span data-stu-id="2abfb-216">This example synchronizes a pull subscription to a merge publication using Web synchronization.</span></span> <span data-ttu-id="2abfb-217">La suscripción se creó sin el trabajo del agente y los metadatos de suscripción relacionados, por lo que se debe iniciar el agente sincrónicamente y se proporciona información adicional acerca de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="2abfb-217">The subscription was created without the agent job and related subscription metadata, so the agent must be started synchronously and additional subscription information is supplied.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub_NoJobWebSync](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub_nojobwebsync)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub_NoJobWebSync](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub_nojobwebsync)]  
  
## <a name="see-also"></a><span data-ttu-id="2abfb-218">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2abfb-218">See Also</span></span>  
 <span data-ttu-id="2abfb-219">[Sincronizar datos](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="2abfb-219">[Synchronize Data](synchronize-data.md) </span></span>  
 <span data-ttu-id="2abfb-220">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="2abfb-220">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 [<span data-ttu-id="2abfb-221">Procedimientos recomendados de seguridad de replicación</span><span class="sxs-lookup"><span data-stu-id="2abfb-221">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
