---
title: Ver y modificar las propiedades de una suscripción de extracción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- modifying subscriptions
- viewing replication properties
- modifying replication properties, pull subscriptions
- pull subscriptions [SQL Server replication], modifying
- subscriptions [SQL Server replication], pull
- pull subscriptions [SQL Server replication], properties
- modifying subscriptions, SQL Server Management Studio
ms.assetid: 1601e54f-86f0-49e8-b023-87a5d1def033
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b847a22d31bbf3ea7540c55339fe27531134125
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662770"
---
# <a name="view-and-modify-pull-subscription-properties"></a><span data-ttu-id="30ab9-102">Ver y modificar las propiedades de una suscripción de extracción</span><span class="sxs-lookup"><span data-stu-id="30ab9-102">View and Modify Pull Subscription Properties</span></span>
  <span data-ttu-id="30ab9-103">En este tema se describe cómo ver y modificar las propiedades de una suscripción de extracción en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="30ab9-103">This topic describes how to view and modify pull subscription properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="30ab9-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="30ab9-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="30ab9-105">**Para ver y modificar las propiedades de una suscripción de extracción con:**</span><span class="sxs-lookup"><span data-stu-id="30ab9-105">**To view and modify pull subscription properties, using:**</span></span>  
  
     [<span data-ttu-id="30ab9-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="30ab9-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="30ab9-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="30ab9-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="30ab9-108">Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="30ab9-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="30ab9-109">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="30ab9-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="30ab9-110">Vea las propiedades de las suscripciones de extracción del publicador o el suscriptor en el cuadro de diálogo **Propiedades de suscripción - \<Publisher>: \<PublicationDatabase>** que está disponible en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30ab9-110">View pull subscription properties from the Publisher or the Subscriber in the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, which is available from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="30ab9-111">En el suscriptor se pueden ver más propiedades y éstas se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="30ab9-111">More properties are visible from the Subscriber, and properties can be modified at the Subscriber.</span></span> <span data-ttu-id="30ab9-112">También se pueden ver propiedades del publicador en la pestaña **Todas las suscripciones** , que está disponible en el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="30ab9-112">You can also view properties from the Publisher on the **All Subscriptions** tab, which is available in Replication Monitor.</span></span> <span data-ttu-id="30ab9-113">Para información sobre cómo iniciar el Monitor de replicación, vea [Iniciar el Monitor de replicación](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="30ab9-113">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-view-pull-subscription-properties-from-the-publisher-in-management-studio"></a><span data-ttu-id="30ab9-114">Para ver las propiedades de las suscripciones de extracción en el publicador en Management Studio</span><span class="sxs-lookup"><span data-stu-id="30ab9-114">To view pull subscription properties from the Publisher in Management Studio</span></span>  
  
1.  <span data-ttu-id="30ab9-115">Conéctese al publicador en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]y luego expanda el nodo del servidor.</span><span class="sxs-lookup"><span data-stu-id="30ab9-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="30ab9-116">Expanda la carpeta **Replicación** y, a continuación, expanda la carpeta **Publicaciones locales** .</span><span class="sxs-lookup"><span data-stu-id="30ab9-116">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="30ab9-117">Expanda la publicación apropiada, haga clic con el botón secundario en una suscripción y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="30ab9-117">Expand the appropriate publication, right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="30ab9-118">Vea las propiedades y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30ab9-118">View properties, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-pull-subscription-properties-from-the-subscriber-in-management-studio"></a><span data-ttu-id="30ab9-119">Para ver y modificar las propiedades de las suscripciones de extracción en el publicador en Management Studio</span><span class="sxs-lookup"><span data-stu-id="30ab9-119">To view and modify pull subscription properties from the Subscriber in Management Studio</span></span>  
  
1.  <span data-ttu-id="30ab9-120">Conéctese al suscriptor en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]y expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="30ab9-120">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="30ab9-121">Expanda la carpeta **Replicación** y, a continuación, la carpeta **Suscripciones locales**.</span><span class="sxs-lookup"><span data-stu-id="30ab9-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="30ab9-122">Haga clic con el botón secundario en una suscripción y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="30ab9-122">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="30ab9-123">Modifique las propiedades si es necesario y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30ab9-123">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-pull-subscription-properties-from-the-publisher-in-replication-monitor"></a><span data-ttu-id="30ab9-124">Para ver las propiedades de las suscripciones de extracción en el publicador en el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="30ab9-124">To view pull subscription properties from the Publisher in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="30ab9-125">Expanda un grupo de publicador en el panel izquierdo del Monitor de replicación, expanda un publicador y, a continuación, haga clic en una publicación.</span><span class="sxs-lookup"><span data-stu-id="30ab9-125">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="30ab9-126">Haga clic en la pestaña **Todas las suscripciones** .</span><span class="sxs-lookup"><span data-stu-id="30ab9-126">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="30ab9-127">Haga clic con el botón secundario en una suscripción y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="30ab9-127">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="30ab9-128">Vea las propiedades y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30ab9-128">View properties, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="30ab9-129">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="30ab9-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="30ab9-130">Se pueden modificar las suscripciones de extracción y tener acceso a sus propiedades mediante programación usando procedimientos almacenados de replicación.</span><span class="sxs-lookup"><span data-stu-id="30ab9-130">Pull subscriptions can be modified and their properties accessed programmatically using replication stored procedures.</span></span> <span data-ttu-id="30ab9-131">Los procedimientos almacenados que se usen dependerán del tipo de publicación a la que corresponda la suscripción.</span><span class="sxs-lookup"><span data-stu-id="30ab9-131">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-view-the-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="30ab9-132">Para ver las propiedades de una suscripción de extracción a una publicación transaccional o de instantáneas</span><span class="sxs-lookup"><span data-stu-id="30ab9-132">To view the properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="30ab9-133">En el suscriptor, ejecute [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30ab9-133">At the Subscriber, execute [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql).</span></span> <span data-ttu-id="30ab9-134">Especifique **@publisher** , **@publisher_db** y **@publication** .</span><span class="sxs-lookup"><span data-stu-id="30ab9-134">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span> <span data-ttu-id="30ab9-135">Esto devuelve información sobre la suscripción que está almacenada en tablas del sistema en el Suscriptor.</span><span class="sxs-lookup"><span data-stu-id="30ab9-135">This returns information about the subscription that is stored in system tables at the Subscriber.</span></span>  
  
2.  <span data-ttu-id="30ab9-136">En el Suscriptor, ejecute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30ab9-136">At the Subscriber, execute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span></span> <span data-ttu-id="30ab9-137">Especifique **@publisher** , **@publisher_db** , **@publication** y uno de los siguientes valores para **@publication_type** :</span><span class="sxs-lookup"><span data-stu-id="30ab9-137">Specify **@publisher**, **@publisher_db**, **@publication**, and one of the following values for **@publication_type**:</span></span>  
  
    -   <span data-ttu-id="30ab9-138">**0** : la suscripción pertenece a una publicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="30ab9-138">**0** - Subscription belongs to a transactional publication.</span></span>  
  
    -   <span data-ttu-id="30ab9-139">**1** : la suscripción pertenece a una publicación de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="30ab9-139">**1** - Subscription belongs to a snapshot publication.</span></span>  
  
3.  <span data-ttu-id="30ab9-140">En el Publicador, ejecute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30ab9-140">At the Publisher, execute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span> <span data-ttu-id="30ab9-141">Especifique **@publication** y **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="30ab9-141">Specify **@publication** and **@subscriber**.</span></span>  
  
4.  <span data-ttu-id="30ab9-142">En el publicador, ejecute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), especificando **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="30ab9-142">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span> <span data-ttu-id="30ab9-143">Presenta información acerca del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="30ab9-143">This displays information about the Subscriber.</span></span>  
  
#### <a name="to-change-the-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="30ab9-144">Para modificar las propiedades de una suscripción de extracción a una publicación transaccional o de instantáneas</span><span class="sxs-lookup"><span data-stu-id="30ab9-144">To change the properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="30ab9-145">En el suscriptor, ejecute [sp_change_subscription_properties](/sql/relational-databases/system-stored-procedures/sp-change-subscription-properties-transact-sql), especificando **@publisher** , **@publisher_db** , **@publication** , un valor de **0** (transaccional) o **1** (instantánea) para **@publication_type** , la propiedad de suscripción que se está cambiando como **@property** y el nuevo valor como **@value** .</span><span class="sxs-lookup"><span data-stu-id="30ab9-145">At the Subscriber, execute [sp_change_subscription_properties](/sql/relational-databases/system-stored-procedures/sp-change-subscription-properties-transact-sql), specifying **@publisher**, **@publisher_db**, **@publication**, a value of either **0** (transactional) or **1** (snapshot) for **@publication_type**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
2.  <span data-ttu-id="30ab9-146">(Opcional) En el suscriptor de la base de datos de suscripciones, ejecute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30ab9-146">(Optional) At the Subscriber on the subscription database, execute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql).</span></span> <span data-ttu-id="30ab9-147">Especifique el identificador del trabajo de Agente de distribución para **@jobid** y las siguientes propiedades del paquete de servicios de transformación de datos (DTS):</span><span class="sxs-lookup"><span data-stu-id="30ab9-147">Specify the ID of the Distribution Agent job for **@jobid**, and the following Data Transformation Services (DTS) package properties:</span></span>  
  
    -   **@dts_package_name**  
  
    -   **@dts_package_password**  
  
    -   **@dts_package_location**  
  
     <span data-ttu-id="30ab9-148">De esta forma se cambian las propiedades del paquete DTS de una suscripción.</span><span class="sxs-lookup"><span data-stu-id="30ab9-148">This changes the DTS package properties of a subscription.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="30ab9-149">El Id del trabajo se puede obtener ejecutando [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30ab9-149">The job ID can be obtained by executing [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span>  
  
#### <a name="to-view-the-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="30ab9-150">Para ver o las propiedades de una suscripción de extracción a una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="30ab9-150">To view the properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="30ab9-151">En el suscriptor, ejecute [sp_helpmergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergepullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30ab9-151">At the Subscriber, execute [sp_helpmergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergepullsubscription-transact-sql).</span></span> <span data-ttu-id="30ab9-152">Especifique **@publisher** , **@publisher_db** y **@publication** .</span><span class="sxs-lookup"><span data-stu-id="30ab9-152">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span>  
  
2.  <span data-ttu-id="30ab9-153">En el Suscriptor, ejecute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30ab9-153">At the Subscriber, execute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span></span> <span data-ttu-id="30ab9-154">Especifique **@publisher** , **@publisher_db** , **@publication** y un valor de 2 para **@publication_type** .</span><span class="sxs-lookup"><span data-stu-id="30ab9-154">Specify **@publisher**, **@publisher_db**, **@publication**, and a value of 2 for **@publication_type**.</span></span>  
  
3.  <span data-ttu-id="30ab9-155">En el Publicador, ejecute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql) para mostrar información de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="30ab9-155">At the Publisher, execute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql) to display subscription information.</span></span> <span data-ttu-id="30ab9-156">Para devolver información sobre una suscripción concreta, debe especificar **@publication** , **@subscriber** y un valor de **pull** para **@subscription_type** .</span><span class="sxs-lookup"><span data-stu-id="30ab9-156">To return information on a specific subscription, you must specify **@publication**, **@subscriber**, and a value of **pull** for **@subscription_type**.</span></span>  
  
4.  <span data-ttu-id="30ab9-157">En el publicador, ejecute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), especificando **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="30ab9-157">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span> <span data-ttu-id="30ab9-158">Presenta información acerca del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="30ab9-158">This displays information about the Subscriber.</span></span>  
  
#### <a name="to-change-the-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="30ab9-159">Para cambiar las propiedades de una suscripción de extracción a una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="30ab9-159">To change the properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="30ab9-160">En el suscriptor, ejecute [sp_changemergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-changemergepullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="30ab9-160">At the Subscriber, execute [sp_changemergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-changemergepullsubscription-transact-sql).</span></span> <span data-ttu-id="30ab9-161">Especifique **@publication** , **@publisher** , **@publisher_db** , la propiedad de suscripción que se está cambiando como **@property** y el nuevo valor como **@value** .</span><span class="sxs-lookup"><span data-stu-id="30ab9-161">Specify **@publication**, **@publisher**, **@publisher_db**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="30ab9-162">Uso de Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="30ab9-162">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="30ab9-163">Las clases RMO que usa para ver o modificar las propiedades de suscripción de extracción dependen del tipo de publicación a la que se suscribe la suscripción de extracción.</span><span class="sxs-lookup"><span data-stu-id="30ab9-163">The RMO classes you use to view or modify pull subscription properties depend on the type of publication to which the pull subscription is subscribed.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="30ab9-164">Para ver o modificar propiedades de una suscripción de extracción a una publicación transaccional o de instantáneas</span><span class="sxs-lookup"><span data-stu-id="30ab9-164">To view or modify properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="30ab9-165">Cree una conexión al suscriptor mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="30ab9-165">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="30ab9-166">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.TransPullSubscription>.</span><span class="sxs-lookup"><span data-stu-id="30ab9-166">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> class.</span></span>  
  
3.  <span data-ttu-id="30ab9-167">Establezca las propiedades <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>y <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="30ab9-167">Set the <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>, and <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="30ab9-168">Establezca la conexión del paso 1 para la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="30ab9-168">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="30ab9-169">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obtener las propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="30ab9-169">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="30ab9-170">Si este método devuelve `false`, se definieron incorrectamente las propiedades de suscripción en el paso 3, o bien la suscripción no existe en el servidor.</span><span class="sxs-lookup"><span data-stu-id="30ab9-170">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist on the server.</span></span>  
  
6.  <span data-ttu-id="30ab9-171">(Opcional) Para cambiar las propiedades, establezca un nuevo valor para una de las propiedades <xref:Microsoft.SqlServer.Replication.TransPullSubscription> que se puedan establecer y, a continuación, llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="30ab9-171">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="30ab9-172">(Opcional) Para ver los nuevos valores, llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> para recargar las propiedades del artículo.</span><span class="sxs-lookup"><span data-stu-id="30ab9-172">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the article.</span></span>  
  
8.  <span data-ttu-id="30ab9-173">Cierre todas las conexiones.</span><span class="sxs-lookup"><span data-stu-id="30ab9-173">Close all connections.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="30ab9-174">Para ver o modificar las propiedades de una suscripción de extracción a una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="30ab9-174">To view or modify properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="30ab9-175">Cree una conexión al suscriptor mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="30ab9-175">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="30ab9-176">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.MergePullSubscription>.</span><span class="sxs-lookup"><span data-stu-id="30ab9-176">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> class.</span></span>  
  
3.  <span data-ttu-id="30ab9-177">Establezca las propiedades <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>y <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="30ab9-177">Set the <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>, and <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="30ab9-178">Establezca la conexión del paso 1 para la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="30ab9-178">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="30ab9-179">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obtener las propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="30ab9-179">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="30ab9-180">Si este método devuelve `false`, se definieron incorrectamente las propiedades de suscripción en el paso 3, o bien la suscripción no existe en el servidor.</span><span class="sxs-lookup"><span data-stu-id="30ab9-180">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist on the server.</span></span>  
  
6.  <span data-ttu-id="30ab9-181">(Opcional) Para cambiar las propiedades, establezca un nuevo valor para una de las propiedades <xref:Microsoft.SqlServer.Replication.MergePullSubscription> que se puedan establecer y, a continuación, llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="30ab9-181">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="30ab9-182">(Opcional) Para ver los nuevos valores, llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> para recargar las propiedades del artículo.</span><span class="sxs-lookup"><span data-stu-id="30ab9-182">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the article.</span></span>  
  
8.  <span data-ttu-id="30ab9-183">Cierre todas las conexiones.</span><span class="sxs-lookup"><span data-stu-id="30ab9-183">Close all connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30ab9-184">Consulte también</span><span class="sxs-lookup"><span data-stu-id="30ab9-184">See Also</span></span>  
 <span data-ttu-id="30ab9-185">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="30ab9-185">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="30ab9-186">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="30ab9-186">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="30ab9-187">Suscribirse a publicaciones</span><span class="sxs-lookup"><span data-stu-id="30ab9-187">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
