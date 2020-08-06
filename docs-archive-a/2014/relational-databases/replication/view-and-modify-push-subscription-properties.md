---
title: Ver y modificar las propiedades de una suscripción de inserción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- viewing replication properties
- push subscriptions [SQL Server replication], properties
- subscriptions [SQL Server replication], push
- push subscriptions [SQL Server replication], modifying
- modifying replication properties, push subscriptions
- modifying subscriptions, SQL Server Management Studio
ms.assetid: 801d2995-7aa5-4626-906e-c8190758ec71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c1506d4f83fcfb94d62efd01c4d6447048fecfd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748722"
---
# <a name="view-and-modify-push-subscription-properties"></a><span data-ttu-id="8db31-102">Ver y modificar las propiedades de una suscripción de inserción</span><span class="sxs-lookup"><span data-stu-id="8db31-102">View and Modify Push Subscription Properties</span></span>
  <span data-ttu-id="8db31-103">En este tema se describe cómo ver y modificar las propiedades de una suscripción de inserción en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="8db31-103">This topic describes how to view and modify push subscription properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="8db31-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="8db31-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8db31-105">**Para ver y modificar las propiedades de una suscripción de inserción con:**</span><span class="sxs-lookup"><span data-stu-id="8db31-105">**To view and modify push subscription properties, using:**</span></span>  
  
     [<span data-ttu-id="8db31-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8db31-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8db31-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8db31-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="8db31-108">Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="8db31-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8db31-109">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8db31-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="8db31-110">Vea y modifique las propiedades de suscripción de inserción del publicador en:</span><span class="sxs-lookup"><span data-stu-id="8db31-110">View and modify push subscription properties from the Publisher in:</span></span>  
  
-   <span data-ttu-id="8db31-111">Cuadro de diálogo **Propiedades de suscripción: \<Publisher>: \<PublicationDatabase>** , que está disponible en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8db31-111">The **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, which is available from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="8db31-112">La pestaña **Todas las suscripciones** en el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="8db31-112">The **All Subscriptions** tab, which is available in Replication Monitor.</span></span> <span data-ttu-id="8db31-113">Para información sobre cómo iniciar el Monitor de replicación, vea [Iniciar el Monitor de replicación](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="8db31-113">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-view-and-modify-push-subscription-properties-in-management-studio"></a><span data-ttu-id="8db31-114">Ver y modificar las propiedades de suscripción de inserción en Management Studio</span><span class="sxs-lookup"><span data-stu-id="8db31-114">To view and modify push subscription properties in Management Studio</span></span>  
  
1.  <span data-ttu-id="8db31-115">Conéctese al publicador en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]y luego expanda el nodo del servidor.</span><span class="sxs-lookup"><span data-stu-id="8db31-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="8db31-116">Expanda la carpeta **Replicación** y, a continuación, expanda la carpeta **Publicaciones locales** .</span><span class="sxs-lookup"><span data-stu-id="8db31-116">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="8db31-117">Expanda la publicación apropiada, haga clic con el botón secundario en una suscripción y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8db31-117">Expand the appropriate publication, right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="8db31-118">Modifique las propiedades si es necesario y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8db31-118">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-push-subscription-properties-in-replication-monitor"></a><span data-ttu-id="8db31-119">Para ver y modificar las propiedades de suscripción de inserción en el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="8db31-119">To view and modify push subscription properties in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="8db31-120">Expanda un grupo de publicador en el panel izquierdo del Monitor de replicación, expanda un publicador y, a continuación, haga clic en una publicación.</span><span class="sxs-lookup"><span data-stu-id="8db31-120">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="8db31-121">Haga clic en la pestaña **Todas las suscripciones** .</span><span class="sxs-lookup"><span data-stu-id="8db31-121">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="8db31-122">Haga clic con el botón secundario en una suscripción y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8db31-122">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="8db31-123">Modifique las propiedades si es necesario y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8db31-123">Modify any properties if necessary, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8db31-124">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8db31-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="8db31-125">Se puede modificar las suscripciones de inserción y tener acceso a sus propiedades mediante programación utilizando procedimientos almacenados de replicación.</span><span class="sxs-lookup"><span data-stu-id="8db31-125">Push subscriptions can be modified and their properties accessed programmatically using replication stored procedures.</span></span> <span data-ttu-id="8db31-126">Los procedimientos almacenados que se usen dependerán del tipo de publicación a la que corresponda la suscripción.</span><span class="sxs-lookup"><span data-stu-id="8db31-126">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-view-the-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="8db31-127">Para ver las propiedades de una suscripción de inserción a una publicación transaccional o de instantáneas</span><span class="sxs-lookup"><span data-stu-id="8db31-127">To view the properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="8db31-128">En la base de datos de publicación del publicador, ejecute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8db31-128">At the Publisher on the publication database, execute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span> <span data-ttu-id="8db31-129">Especifique **@publication** , **@subscriber** y un valor de **All** para **@article** .</span><span class="sxs-lookup"><span data-stu-id="8db31-129">Specify **@publication**, **@subscriber**, and a value of **all** for **@article**.</span></span>  
  
2.  <span data-ttu-id="8db31-130">En la base de datos de publicación del publicador, ejecute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), especificando **@subscriber**.</span><span class="sxs-lookup"><span data-stu-id="8db31-130">At the Publisher on the publication database, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span>  
  
#### <a name="to-change-the-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="8db31-131">Para modificar las propiedades de una suscripción de inserción a una publicación transaccional o de instantáneas</span><span class="sxs-lookup"><span data-stu-id="8db31-131">To change the properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="8db31-132">En la base de datos de publicación del publicador, ejecute [sp_changesubscriber](/sql/relational-databases/system-stored-procedures/sp-changesubscriber-transact-sql), especificando **@subscriber** y los parámetros de las propiedades del suscriptor que se vayan a cambiar.</span><span class="sxs-lookup"><span data-stu-id="8db31-132">At the Publisher on the publication database, execute [sp_changesubscriber](/sql/relational-databases/system-stored-procedures/sp-changesubscriber-transact-sql), specifying **@subscriber** and any parameters for the Subscriber properties being changed.</span></span>  
  
2.  <span data-ttu-id="8db31-133">En la base de datos de publicación del publicador, ejecute [sp_changesubscription](/sql/relational-databases/system-stored-procedures/sp-changesubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8db31-133">At the Publisher on the publication database, execute [sp_changesubscription](/sql/relational-databases/system-stored-procedures/sp-changesubscription-transact-sql).</span></span> <span data-ttu-id="8db31-134">Especifique **@publication** , **@subscriber** , **@destination_db** , un valor de **All** para **@article** , la propiedad de suscripción que se está cambiando como **@property** y el nuevo valor como **@value** .</span><span class="sxs-lookup"><span data-stu-id="8db31-134">Specify **@publication**, **@subscriber**, **@destination_db**, a value of **all** for **@article**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span> <span data-ttu-id="8db31-135">Esto cambia la configuración de seguridad para la suscripción de inserción.</span><span class="sxs-lookup"><span data-stu-id="8db31-135">This changes security settings for the push subscription.</span></span>  
  
3.  <span data-ttu-id="8db31-136">(Opcional) Para cambiar las propiedades del paquete de Servicios de transformación de datos (DTS) de una suscripción, ejecute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql) en la base de datos de suscripciones del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="8db31-136">(Optional) To change the Data Transformation Services (DTS) package properties of a subscription, execute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql) at the Subscriber on the subscription database.</span></span> <span data-ttu-id="8db31-137">Especifique el identificador del trabajo de Agente de distribución para **@jobid** y las siguientes propiedades del paquete DTS:</span><span class="sxs-lookup"><span data-stu-id="8db31-137">Specify the ID of the Distribution Agent job for **@jobid** and the following DTS package properties:</span></span>  
  
    -   **@dts_package_name**  
  
    -   **@dts_package_password**  
  
    -   **@dts_package_location**  
  
     <span data-ttu-id="8db31-138">De esta forma se cambian las propiedades del paquete DTS de una suscripción.</span><span class="sxs-lookup"><span data-stu-id="8db31-138">This changes the DTS package properties of a subscription.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8db31-139">El Id del trabajo se puede obtener ejecutando [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8db31-139">The job ID can be obtained by executing [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span>  
  
#### <a name="to-view-the-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="8db31-140">Para ver o las propiedades de una suscripción de inserción a una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="8db31-140">To view the properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="8db31-141">En la base de datos de publicación del publicador, ejecute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8db31-141">At the Publisher on the publication database, execute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql).</span></span> <span data-ttu-id="8db31-142">Especifique **@publication** y **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="8db31-142">Specify **@publication** and **@subscriber**.</span></span>  
  
2.  <span data-ttu-id="8db31-143">En el publicador, ejecute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), especificando **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="8db31-143">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span>  
  
#### <a name="to-change-the-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="8db31-144">Para cambiar las propiedades de una suscripción de inserción a una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="8db31-144">To change the properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="8db31-145">En la base de datos de publicación del publicador, ejecute [sp_changemergesubscription](/sql/relational-databases/system-stored-procedures/sp-changemergesubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8db31-145">At the Publisher on the publication database, execute [sp_changemergesubscription](/sql/relational-databases/system-stored-procedures/sp-changemergesubscription-transact-sql).</span></span> <span data-ttu-id="8db31-146">Especifique **@publication** , **@subscriber** , **@subscriber_db** , la propiedad de suscripción que se está cambiando como **@property** y el nuevo valor como **@value** .</span><span class="sxs-lookup"><span data-stu-id="8db31-146">Specify **@publication**, **@subscriber**, **@subscriber_db**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="8db31-147">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8db31-147">Example (Transact-SQL)</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="8db31-148">Uso de Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="8db31-148">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="8db31-149">Las clases RMO que usa para ver o modificar las propiedades de suscripción de inserción dependen del tipo de publicación a la que se suscribe la suscripción de inserción.</span><span class="sxs-lookup"><span data-stu-id="8db31-149">The RMO classes you use to view or modify push subscription properties depend on the type of publication to which the push subscription is subscribed.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="8db31-150">Para ver o modificar propiedades de una suscripción de inserción a una publicación transaccional o de instantáneas</span><span class="sxs-lookup"><span data-stu-id="8db31-150">To view or modify properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="8db31-151">Cree una conexión al publicador mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="8db31-151">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="8db31-152">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.TransSubscription>.</span><span class="sxs-lookup"><span data-stu-id="8db31-152">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class.</span></span>  
  
3.  <span data-ttu-id="8db31-153">Establezca las propiedades <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>y <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="8db31-153">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="8db31-154">Establezca la conexión <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del paso 1 para la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="8db31-154">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property setting.</span></span>  
  
5.  <span data-ttu-id="8db31-155">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obtener las propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="8db31-155">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="8db31-156">Si este método devuelve `false`, significa que las propiedades de suscripción del paso 3 se definieron incorrectamente, o bien que la suscripción no existe.</span><span class="sxs-lookup"><span data-stu-id="8db31-156">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="8db31-157">(Opcional) Para cambiar las propiedades, establezca un nuevo valor para una de las propiedades <xref:Microsoft.SqlServer.Replication.TransSubscription> que se puedan establecer y, a continuación, llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="8db31-157">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.TransSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="8db31-158">(Opcional) Para ver los nuevos valores, llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> para recargar las propiedades de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="8db31-158">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the subscription.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="8db31-159">Para ver o modificar las propiedades de una suscripción de inserción a una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="8db31-159">To view or modify properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="8db31-160">Cree una conexión al suscriptor mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="8db31-160">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="8db31-161">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.MergeSubscription>.</span><span class="sxs-lookup"><span data-stu-id="8db31-161">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class.</span></span>  
  
3.  <span data-ttu-id="8db31-162">Establezca las propiedades <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>y <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="8db31-162">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="8db31-163">Establezca la conexión <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del paso 1 para la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="8db31-163">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property setting.</span></span>  
  
5.  <span data-ttu-id="8db31-164">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obtener las propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="8db31-164">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="8db31-165">Si este método devuelve `false`, significa que las propiedades de suscripción del paso 3 se definieron incorrectamente, o bien que la suscripción no existe.</span><span class="sxs-lookup"><span data-stu-id="8db31-165">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="8db31-166">(Opcional) Para cambiar las propiedades, establezca un nuevo valor para una de las propiedades <xref:Microsoft.SqlServer.Replication.MergeSubscription> que se puedan establecer y, a continuación, llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="8db31-166">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="8db31-167">(Opcional) Para ver los nuevos valores, llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> para recargar las propiedades de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="8db31-167">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8db31-168">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8db31-168">See Also</span></span>  
 <span data-ttu-id="8db31-169">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="8db31-169">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="8db31-170">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="8db31-170">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="8db31-171">Suscribirse a publicaciones</span><span class="sxs-lookup"><span data-stu-id="8db31-171">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
