---
title: Suscribirse a publicaciones | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.conc.subtopubs.f1
helpviewer_keywords:
- subscriptions [SQL Server replication], about subscriptions
- pull subscriptions [SQL Server replication]
- subscriptions [SQL Server replication]
- push subscriptions [SQL Server replication], about push subscriptions
- merge replication subscribing [SQL Server replication]
- merge replication subscribing [SQL Server replication], about subscribing
- publications [SQL Server replication], subscribing
- push subscriptions [SQL Server replication]
- pull subscriptions [SQL Server replication], about pull subscriptions
- snapshot replication [SQL Server], subscribing
- transactional replication, subscribing
ms.assetid: 088ee30a-05ab-47c4-92ed-316b93e12445
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c565aae26c6d549eb67043168797d5fb059c8e2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662775"
---
# <a name="subscribe-to-publications"></a><span data-ttu-id="5953d-102">Suscribirse a publicaciones</span><span class="sxs-lookup"><span data-stu-id="5953d-102">Subscribe to Publications</span></span>
  <span data-ttu-id="5953d-103">Una suscripción es una solicitud de copia de datos y objetos de base de datos en una publicación.</span><span class="sxs-lookup"><span data-stu-id="5953d-103">A subscription is a request for a copy of the data and database objects in a publication.</span></span> <span data-ttu-id="5953d-104">Una suscripción define qué publicación se recibirá, dónde y cuándo.</span><span class="sxs-lookup"><span data-stu-id="5953d-104">A subscription defines which publication will be received, and where and when it will be received.</span></span> <span data-ttu-id="5953d-105">Al planear suscripciones, tenga en cuenta dónde se realizará el proceso del agente.</span><span class="sxs-lookup"><span data-stu-id="5953d-105">When planning for subscriptions, consider where you want agent processing to occur.</span></span> <span data-ttu-id="5953d-106">El tipo de suscripción que elige controla dónde se ejecuta el agente.</span><span class="sxs-lookup"><span data-stu-id="5953d-106">The type of subscription you choose controls where the agent runs.</span></span> <span data-ttu-id="5953d-107">Con una suscripción de inserción, el Agente de mezcla o el Agente de distribución se ejecutan en el distribuidor, mientras que en una suscripción de extracción los agentes se ejecutan en los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="5953d-107">With a push subscription, the Merge Agent or Distribution Agent runs at the Distributor, whereas with a pull subscription, agents run at the Subscribers.</span></span> <span data-ttu-id="5953d-108">Después de crear una suscripción, no se puede cambiar de un tipo a otro.</span><span class="sxs-lookup"><span data-stu-id="5953d-108">After a subscription is created, it cannot be changed from one type to another.</span></span>  
  
|<span data-ttu-id="5953d-109">Suscripción</span><span class="sxs-lookup"><span data-stu-id="5953d-109">Subscription</span></span>|<span data-ttu-id="5953d-110">Características</span><span class="sxs-lookup"><span data-stu-id="5953d-110">Characteristics</span></span>|<span data-ttu-id="5953d-111">Se utiliza si</span><span class="sxs-lookup"><span data-stu-id="5953d-111">Use When</span></span>|  
|------------------|---------------------|--------------|  
|<span data-ttu-id="5953d-112">Suscripción de inserción</span><span class="sxs-lookup"><span data-stu-id="5953d-112">Push Subscription</span></span>|<span data-ttu-id="5953d-113">Con una suscripción de inserción, el publicador propaga los cambios al suscriptor sin que éste lo solicite.</span><span class="sxs-lookup"><span data-stu-id="5953d-113">With a push subscription, the Publisher propagates changes to a Subscriber without a request from the Subscriber.</span></span> <span data-ttu-id="5953d-114">Los cambios pueden insertarse en los suscriptores a petición, de manera continua o según una programación.</span><span class="sxs-lookup"><span data-stu-id="5953d-114">Changes can be pushed to Subscribers on demand, continuously, or on a scheduled basis.</span></span> <span data-ttu-id="5953d-115">De forma predeterminada, el Agente de distribución o el Agente de mezcla se ejecutan en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="5953d-115">The Distribution Agent or Merge Agent runs at the Distributor.</span></span>|<span data-ttu-id="5953d-116">Normalmente, los datos se sincronizarán de forma continua o con una frecuencia determinada.</span><span class="sxs-lookup"><span data-stu-id="5953d-116">Data will typically be synchronized continuously or on a frequently recurring schedule.</span></span><br /><br /> <span data-ttu-id="5953d-117">Las publicaciones requieren que el movimiento de datos sea casi en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="5953d-117">Publications require near real-time movement of data.</span></span><br /><br /> <span data-ttu-id="5953d-118">La sobrecarga del procesador en el distribuidor no afecta al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5953d-118">The higher processor overhead at the Distributor does not affect performance.</span></span><br /><br /> <span data-ttu-id="5953d-119">Se utiliza frecuentemente en la replicación de instantáneas y transaccional.</span><span class="sxs-lookup"><span data-stu-id="5953d-119">Most often used with snapshot and transactional replication.</span></span>|  
|<span data-ttu-id="5953d-120">Suscripción de extracción</span><span class="sxs-lookup"><span data-stu-id="5953d-120">Pull Subscription</span></span>|<span data-ttu-id="5953d-121">En una suscripción de extracción, el suscriptor solicita los cambios efectuados en el publicador.</span><span class="sxs-lookup"><span data-stu-id="5953d-121">With a pull subscription, the Subscriber requests changes made at the Publisher.</span></span> <span data-ttu-id="5953d-122">Las suscripciones de extracción permiten al usuario del suscriptor determinar cuándo se sincronizan los cambios en los datos.</span><span class="sxs-lookup"><span data-stu-id="5953d-122">Pull subscriptions allow the user at the Subscriber to determine when the data changes are synchronized.</span></span> <span data-ttu-id="5953d-123">El Agente de distribución o el Agente de mezcla se ejecutan en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="5953d-123">The Distribution Agent or the Merge Agent runs at the Subscriber.</span></span>|<span data-ttu-id="5953d-124">Los datos se sincronizarán, generalmente, a petición o en función de una programación, en lugar de hacerlo de forma continuada.</span><span class="sxs-lookup"><span data-stu-id="5953d-124">Data will typically be synchronized on demand or on a schedule rather than continuously.</span></span><br /><br /> <span data-ttu-id="5953d-125">La publicación dispone de un gran número de suscriptores y/o la ejecución de todos los agentes en el distribuidor supone un uso demasiado intensivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="5953d-125">The publication has a large number of Subscribers, and/or it would be too resource-intensive to run all the agents at the Distributor.</span></span><br /><br /> <span data-ttu-id="5953d-126">Los suscriptores son autónomos, están desconectados o se desplazan.</span><span class="sxs-lookup"><span data-stu-id="5953d-126">Subscribers are autonomous, disconnected, and/or mobile.</span></span> <span data-ttu-id="5953d-127">Los suscriptores determinan cuándo se conectarán y sincronizarán los cambios.</span><span class="sxs-lookup"><span data-stu-id="5953d-127">Subscribers will determine when they will connect and synchronize changes.</span></span><br /><br /> <span data-ttu-id="5953d-128">Se utiliza frecuentemente en la replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="5953d-128">Most often used with merge replication.</span></span>|  
  
## <a name="merge-replication-subscription-types"></a><span data-ttu-id="5953d-129">Tipos de suscripción de replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="5953d-129">Merge Replication Subscription Types</span></span>  
 <span data-ttu-id="5953d-130">Todos los tipos de replicación permiten suscripciones de inserción y extracción.</span><span class="sxs-lookup"><span data-stu-id="5953d-130">All replication types allow push and pull subscriptions.</span></span> <span data-ttu-id="5953d-131">La replicación de mezcla utiliza dos términos adicionales para distinguir las suscripciones: suscripciones de cliente y suscripciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="5953d-131">Merge replication uses two additional terms to distinguish subscriptions: client subscriptions and server subscriptions.</span></span> <span data-ttu-id="5953d-132">Ambos tipos de suscripción se pueden utilizar con suscripciones de inserción o extracción.</span><span class="sxs-lookup"><span data-stu-id="5953d-132">Both client and server subscription types can be used with push and pull subscriptions.</span></span> <span data-ttu-id="5953d-133">Las suscripciones de cliente son adecuadas para la mayoría de suscriptores, mientras que las suscripciones de servidor se utilizan normalmente en suscriptores que vuelven a publicar datos en otros suscriptores.</span><span class="sxs-lookup"><span data-stu-id="5953d-133">Client subscriptions are appropriate for most Subscribers, whereas server subscriptions are typically used for Subscribers that republish data to other Subscribers.</span></span> <span data-ttu-id="5953d-134">La elección de la suscripción también afecta a la resolución de conflictos.</span><span class="sxs-lookup"><span data-stu-id="5953d-134">Subscription choice also affects conflict resolution.</span></span>  
  
## <a name="non-sql-server-subscribers"></a><span data-ttu-id="5953d-135">suscriptores que no son de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5953d-135">Non-SQL Server Subscribers</span></span>  
 <span data-ttu-id="5953d-136">Oracle e IBM DB2 pueden suscribirse a publicaciones de instantáneas y transaccionales con suscripciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="5953d-136">Oracle and IBM DB2 can subscribe to snapshot and transactional publications using push subscriptions.</span></span> <span data-ttu-id="5953d-137">Para más información, consulte [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="5953d-137">For more information, see [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span></span>  
  
## <a name="creating-subscriptions"></a><span data-ttu-id="5953d-138">Crear suscripciones</span><span class="sxs-lookup"><span data-stu-id="5953d-138">Creating Subscriptions</span></span>  
 <span data-ttu-id="5953d-139">Para crear una suscripción, proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="5953d-139">To create a subscription, you supply the following information:</span></span>  
  
-   <span data-ttu-id="5953d-140">Nombre de la publicación.</span><span class="sxs-lookup"><span data-stu-id="5953d-140">The name of the publication.</span></span>  
  
-   <span data-ttu-id="5953d-141">El nombre del suscriptor y la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="5953d-141">The name of the Subscriber and the subscription database.</span></span>  
  
-   <span data-ttu-id="5953d-142">Si el Agente de distribución o el Agente de mezcla se ejecutan en el distribuidor o en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="5953d-142">Whether the Distribution Agent or Merge Agent runs at the Distributor or at the Subscriber.</span></span>  
  
-   <span data-ttu-id="5953d-143">Si el Agente de distribución o el Agente de mezcla se ejecutan de forma continua, programada o solamente a petición.</span><span class="sxs-lookup"><span data-stu-id="5953d-143">Whether the Distribution Agent or Merge Agent runs continuously, on a scheduled basis, or on demand only.</span></span>  
  
-   <span data-ttu-id="5953d-144">Si el Agente de instantáneas debe crear una instantánea inicial para la suscripción y si el Agente de distribución o el Agente de mezcla debe aplicar esa instantánea en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="5953d-144">Whether the Snapshot Agent should create an initial snapshot for the subscription and whether the Distribution Agent or Merge Agent should apply that snapshot at the Subscriber.</span></span>  
  
-   <span data-ttu-id="5953d-145">Las cuentas con la que se ejecutará el Agente de distribución o el Agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="5953d-145">Accounts under which the Distribution Agent or Merge Agent will run.</span></span>  
  
-   <span data-ttu-id="5953d-146">En la replicación de mezcla, el tipo de suscripción: servidor o cliente.</span><span class="sxs-lookup"><span data-stu-id="5953d-146">For merge replication, the type of subscription: server or client.</span></span>  
  
 <span data-ttu-id="5953d-147">**Para crear una suscripción de inserción**</span><span class="sxs-lookup"><span data-stu-id="5953d-147">**To create a push subscription**</span></span>  
  
 <span data-ttu-id="5953d-148">[Create a Push Subscription](create-a-push-subscription.md) (Creación de una suscripción de inserción)</span><span class="sxs-lookup"><span data-stu-id="5953d-148">[Create a Push Subscription](create-a-push-subscription.md)</span></span>  
  
 <span data-ttu-id="5953d-149">**Para ver o modificar las propiedades de una suscripción de inserción**</span><span class="sxs-lookup"><span data-stu-id="5953d-149">**To view or modify push subscription properties**</span></span>  
  
 [<span data-ttu-id="5953d-150">Ver y modificar las propiedades de una suscripción de inserción</span><span class="sxs-lookup"><span data-stu-id="5953d-150">View and Modify Push Subscription Properties</span></span>](view-and-modify-push-subscription-properties.md)  
  
 <span data-ttu-id="5953d-151">**Para eliminar una suscripción de inserción**</span><span class="sxs-lookup"><span data-stu-id="5953d-151">**To delete a push subscription**</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="5953d-152">: [Eliminar una suscripción de inserción](delete-a-push-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="5953d-152">: [Delete a Push Subscription](delete-a-push-subscription.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5953d-153">Al eliminar una suscripción no se quitan los objetos publicados del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="5953d-153">Deleting a subscription does not remove published objects from the Subscriber.</span></span>  
  
 <span data-ttu-id="5953d-154">**Para crear una suscripción de extracción**</span><span class="sxs-lookup"><span data-stu-id="5953d-154">**To create a pull subscription**</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="5953d-155">: [Crear una suscripción de extracción](create-a-pull-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="5953d-155">: [Create a Pull Subscription](create-a-pull-subscription.md)</span></span>  
  
 <span data-ttu-id="5953d-156">**Para ver o modificar las propiedades de una suscripción de extracción**</span><span class="sxs-lookup"><span data-stu-id="5953d-156">**To view or modify pull subscription properties**</span></span>  
  
 [<span data-ttu-id="5953d-157">Ver y modificar las propiedades de una suscripción de extracción</span><span class="sxs-lookup"><span data-stu-id="5953d-157">View and Modify Pull Subscription Properties</span></span>](view-and-modify-pull-subscription-properties.md)  
  
 <span data-ttu-id="5953d-158">**Para eliminar una suscripción de extracción**</span><span class="sxs-lookup"><span data-stu-id="5953d-158">**To delete a pull subscription**</span></span>  
  
 [<span data-ttu-id="5953d-159">Eliminar una suscripción de extracción</span><span class="sxs-lookup"><span data-stu-id="5953d-159">Delete a Pull Subscription</span></span>](delete-a-pull-subscription.md)  
  
## <a name="see-also"></a><span data-ttu-id="5953d-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5953d-160">See Also</span></span>  
 <span data-ttu-id="5953d-161">[Proteger el suscriptor](security/secure-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="5953d-161">[Secure the Subscriber](security/secure-the-subscriber.md) </span></span>  
 [<span data-ttu-id="5953d-162">Desactivación y expiración de la suscripción</span><span class="sxs-lookup"><span data-stu-id="5953d-162">Subscription Expiration and Deactivation</span></span>](subscription-expiration-and-deactivation.md)  
  
  
