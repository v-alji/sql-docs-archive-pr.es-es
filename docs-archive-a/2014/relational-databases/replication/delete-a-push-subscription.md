---
title: Eliminación de una suscripción de inserción | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- removing subscriptions
- push subscriptions [SQL Server replication], deleting
- deleting subscriptions
- subscriptions [SQL Server replication], push
ms.assetid: 3c4847e2-aed9-4488-b45d-8164422bdb10
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 912958e00d117f51c5dc95c0dc1247d278acb0ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663396"
---
# <a name="delete-a-push-subscription"></a><span data-ttu-id="02db1-102">Eliminar una suscripción de inserción</span><span class="sxs-lookup"><span data-stu-id="02db1-102">Delete a Push Subscription</span></span>
  <span data-ttu-id="02db1-103">En este tema se describe cómo eliminar una suscripción de inserción en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="02db1-103">This topic describes how to delete a push subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="02db1-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="02db1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="02db1-105">**Para eliminar una suscripción de inserción con:**</span><span class="sxs-lookup"><span data-stu-id="02db1-105">**To delete a push subscription, using:**</span></span>  
  
     [<span data-ttu-id="02db1-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="02db1-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="02db1-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="02db1-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="02db1-108">Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="02db1-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="02db1-109">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="02db1-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="02db1-110">Elimine una suscripción de inserción en el publicador (desde la carpeta **Publicaciones locales** en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]) o el suscriptor (desde la carpeta **Suscripciones locales** ).</span><span class="sxs-lookup"><span data-stu-id="02db1-110">Delete a push subscription at the Publisher (from the **Local Publications** folder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]) or the Subscriber (from the **Local Subscriptions** folder).</span></span> <span data-ttu-id="02db1-111">Al eliminar una suscripción no se quitan los objetos ni los datos de la suscripción, y deben quitarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="02db1-111">Deleting a subscription does not remove objects or data from the subscription; they must be removed manually.</span></span>  
  
#### <a name="to-delete-a-push-subscription-at-the-publisher"></a><span data-ttu-id="02db1-112">Para eliminar una suscripción de inserción en el publicador</span><span class="sxs-lookup"><span data-stu-id="02db1-112">To delete a push subscription at the Publisher</span></span>  
  
1.  <span data-ttu-id="02db1-113">Conéctese al publicador en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]y luego expanda el nodo del servidor.</span><span class="sxs-lookup"><span data-stu-id="02db1-113">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="02db1-114">Expanda la carpeta **Replicación** y, a continuación, expanda la carpeta **Publicaciones locales** .</span><span class="sxs-lookup"><span data-stu-id="02db1-114">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="02db1-115">Expanda la publicación asociada con la suscripción que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="02db1-115">Expand the publication associated with the subscription you want to delete.</span></span>  
  
4.  <span data-ttu-id="02db1-116">Haga clic con el botón secundario en la suscripción y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="02db1-116">Right-click the subscription, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="02db1-117">En el cuadro de diálogo de confirmación, seleccione si desea conectarse al suscriptor para eliminar la información de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="02db1-117">In the confirmation dialog box, select whether to connect to the Subscriber to delete subscription information.</span></span> <span data-ttu-id="02db1-118">Si desactiva la casilla **Conectar a suscriptor** , debe conectar al suscriptor posteriormente para eliminar la información.</span><span class="sxs-lookup"><span data-stu-id="02db1-118">If you clear the **Connect to Subscriber** checkbox, you should connect to the Subscriber later to delete the information.</span></span>  
  
#### <a name="to-delete-a-push-subscription-at-the-subscriber"></a><span data-ttu-id="02db1-119">Para eliminar una suscripción de inserción en el suscriptor</span><span class="sxs-lookup"><span data-stu-id="02db1-119">To delete a push subscription at the Subscriber</span></span>  
  
1.  <span data-ttu-id="02db1-120">Conéctese al suscriptor en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]y expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="02db1-120">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="02db1-121">Expanda la carpeta **Replicación** y, a continuación, la carpeta **Suscripciones locales**.</span><span class="sxs-lookup"><span data-stu-id="02db1-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="02db1-122">Haga clic con el botón secundario en la suscripción que desea eliminar y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="02db1-122">Right-click the subscription you want to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="02db1-123">En el cuadro de diálogo de confirmación, seleccione si desea conectarse al publicador para eliminar la información de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="02db1-123">In the confirmation dialog box, select whether to connect to the Publisher to delete subscription information.</span></span> <span data-ttu-id="02db1-124">Si desactiva la casilla **Conectar al publicador** , deberá conectarse al publicador más adelante para eliminar la información.</span><span class="sxs-lookup"><span data-stu-id="02db1-124">If you clear the **Connect to Publisher** check box, you should connect to the Publisher later to delete the information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="02db1-125">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="02db1-125">Using Transact-SQL</span></span>  
 <span data-ttu-id="02db1-126">Las suscripciones de inserción pueden eliminarse mediante programación con procedimientos almacenados de replicación.</span><span class="sxs-lookup"><span data-stu-id="02db1-126">Push subscriptions can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="02db1-127">Los procedimientos almacenados que se usen dependerán del tipo de publicación a la que corresponda la suscripción.</span><span class="sxs-lookup"><span data-stu-id="02db1-127">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="02db1-128">Para eliminar una suscripción de inserción a una publicación transaccional o de instantáneas</span><span class="sxs-lookup"><span data-stu-id="02db1-128">To delete a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="02db1-129">(Opcional) en la base de datos de publicación del publicador, ejecute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="02db1-129">At the Publisher on the publication database, execute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span></span> <span data-ttu-id="02db1-130">Especifique **@publication** y **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="02db1-130">Specify **@publication** and **@subscriber**.</span></span> <span data-ttu-id="02db1-131">Especifique un valor de **all** para **@article**.</span><span class="sxs-lookup"><span data-stu-id="02db1-131">Specify a value of **all** for **@article**.</span></span> <span data-ttu-id="02db1-132">(Opcional) Si no se puede tener acceso al Distribuidor, especifique un valor de **1** para **@ignore_distributor** para eliminar la suscripción sin quitar los objetos relacionados en el Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="02db1-132">(Optional) If the Distributor cannot be accessed, specify a value of **1** for **@ignore_distributor** to delete the subscription without removing related objects at the Distributor.</span></span>  
  
2.  <span data-ttu-id="02db1-133">(Opcional) En la base de datos de suscripciones del suscriptor, ejecute [sp_subscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) para quitar los metadatos de replicación restantes en la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="02db1-133">At the Subscriber on the subscription database, execute [sp_subscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) to remove replication metadata in the subscription database.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="02db1-134">Para eliminar una suscripción de inserción a una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="02db1-134">To delete a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="02db1-135">En el publicador, ejecute [sp_dropmergesubscription &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-dropmergesubscription-transact-sql), especificando **@publication** , **@subscriber** y **@subscriber_db** .</span><span class="sxs-lookup"><span data-stu-id="02db1-135">At the Publisher, execute [sp_dropmergesubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergesubscription-transact-sql), specifying **@publication**, **@subscriber** and **@subscriber_db**.</span></span> <span data-ttu-id="02db1-136">(Opcional) Si no se puede tener acceso al Distribuidor, especifique un valor de **1** para **@ignore_distributor** para eliminar la suscripción sin quitar los objetos relacionados en el Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="02db1-136">(Optional) If the Distributor cannot be accessed, specify a value of **1** for **@ignore_distributor** to delete the subscription without removing related objects at the Distributor.</span></span>  
  
2.  <span data-ttu-id="02db1-137">En la base de datos de suscripciones del suscriptor, ejecute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="02db1-137">At the Subscriber on the subscription database, execute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql).</span></span> <span data-ttu-id="02db1-138">Especifique **@publisher** , **@publisher_db** y **@publication** .</span><span class="sxs-lookup"><span data-stu-id="02db1-138">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span> <span data-ttu-id="02db1-139">Esto quita los metadatos de mezcla de la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="02db1-139">This removes merge metadata from the subscription database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="02db1-140">Ejemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="02db1-140">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="02db1-141">En este ejemplo se elimina una suscripción de inserción a una publicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="02db1-141">This example deletes a push subscription to a transactional publication.</span></span>  
  
 [!code-sql[HowTo#sp_droptransubscription](../../snippets/tsql/SQL15/replication/howto/tsql/droptranpullsub.sql#sp_droptransubscription)]  
  
 <span data-ttu-id="02db1-142">En este ejemplo se elimina una suscripción de inserción a una publicación de combinación.</span><span class="sxs-lookup"><span data-stu-id="02db1-142">This example deletes a push subscription to a merge publication.</span></span>  
  
 [!code-sql[HowTo#sp_dropmergesubscription](../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepullsub.sql#sp_dropmergesubscription)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="02db1-143">Uso de Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="02db1-143">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="02db1-144">Las clases RMO que se usan para eliminar una suscripción de inserción dependen del tipo de publicación a la se suscribe dicha suscripción.</span><span class="sxs-lookup"><span data-stu-id="02db1-144">The RMO classes that you use to delete a push subscription depend on the type of publication to which the push subscription is subscribed.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="02db1-145">Para eliminar una suscripción de inserción a una publicación transaccional o de instantáneas</span><span class="sxs-lookup"><span data-stu-id="02db1-145">To delete a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="02db1-146">Cree una conexión al suscriptor mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="02db1-146">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="02db1-147">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.TransSubscription>.</span><span class="sxs-lookup"><span data-stu-id="02db1-147">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class.</span></span>  
  
3.  <span data-ttu-id="02db1-148">Establezca las propiedades <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>y <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="02db1-148">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="02db1-149">Establezca la conexión <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del paso 1 para la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="02db1-149">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="02db1-150">Compruebe la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> para asegurarse de que la suscripción existe.</span><span class="sxs-lookup"><span data-stu-id="02db1-150">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the subscription exists.</span></span> <span data-ttu-id="02db1-151">Si el valor de esta propiedad es `false`, significa que las propiedades de suscripción del paso 2 se definieron incorrectamente o bien, que la suscripción no existe.</span><span class="sxs-lookup"><span data-stu-id="02db1-151">If the value of this property is `false`, either the subscription properties in step 2 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="02db1-152">Llame al método <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="02db1-152">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> method.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="02db1-153">Para eliminar una suscripción de inserción a una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="02db1-153">To delete a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="02db1-154">Cree una conexión al suscriptor mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="02db1-154">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="02db1-155">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.MergeSubscription>.</span><span class="sxs-lookup"><span data-stu-id="02db1-155">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class.</span></span>  
  
3.  <span data-ttu-id="02db1-156">Establezca las propiedades <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>y <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="02db1-156">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="02db1-157">Establezca la conexión <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del paso 1 para la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="02db1-157">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="02db1-158">Compruebe la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> para asegurarse de que la suscripción existe.</span><span class="sxs-lookup"><span data-stu-id="02db1-158">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the subscription exists.</span></span> <span data-ttu-id="02db1-159">Si el valor de esta propiedad es `false`, significa que las propiedades de suscripción del paso 2 se definieron incorrectamente o bien, que la suscripción no existe.</span><span class="sxs-lookup"><span data-stu-id="02db1-159">If the value of this property is `false`, either the subscription properties in step 2 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="02db1-160">Llame al método <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="02db1-160">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> method.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="02db1-161">Ejemplos (RMO)</span><span class="sxs-lookup"><span data-stu-id="02db1-161">Examples (RMO)</span></span>  
 <span data-ttu-id="02db1-162">Las suscripciones de inserción se pueden eliminar mediante programación utilizando Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="02db1-162">You can delete push subscriptions programmatically by using Replication Management Objects (RMO).</span></span>  
  
 [!code-csharp[HowTo#rmo_DropTranPushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_droptranpushsub)]  
  
 [!code-vb[HowTo#rmo_vb_DropTranPushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_droptranpushsub)]  
  
## <a name="see-also"></a><span data-ttu-id="02db1-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02db1-163">See Also</span></span>  
 <span data-ttu-id="02db1-164">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="02db1-164">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="02db1-165">Procedimientos recomendados de seguridad de replicación</span><span class="sxs-lookup"><span data-stu-id="02db1-165">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
