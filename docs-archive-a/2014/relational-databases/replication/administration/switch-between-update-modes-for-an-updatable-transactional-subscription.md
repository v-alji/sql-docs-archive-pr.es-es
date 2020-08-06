---
title: Cambiar entre modos de actualización para una suscripción transaccional actualizable | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transactional replication, updatable subscriptions
- updatable subscriptions, update modes
- subscriptions [SQL Server replication], updatable
ms.assetid: ab5ebab1-7ee4-41f4-999b-b4f0c420c921
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c31814d1e2ab6fac64ffcde883f3cac2439828a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678171"
---
# <a name="switch-between-update-modes-for-an-updatable-transactional-subscription"></a><span data-ttu-id="16e47-102">Cambiar entre modos de actualización para una suscripción transaccional actualizable</span><span class="sxs-lookup"><span data-stu-id="16e47-102">Switch Between Update Modes for an Updatable Transactional Subscription</span></span>
  <span data-ttu-id="16e47-103">En este tema se describe cómo cambiar entre modos en actualización para una suscripción de transacción actualizable en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16e47-103">This topic describes how to switch between update modes for an updatable transaction subscription in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="16e47-104">Especifique el modo que desea utilizar para las suscripciones actualizables con el Asistente para nuevas suscripciones.</span><span class="sxs-lookup"><span data-stu-id="16e47-104">Specify the mode for updatable subscriptions using the New Subscription Wizard.</span></span> <span data-ttu-id="16e47-105">Para información sobre cómo establecer el modo cuando se utiliza este asistente, vea [View and Modify Pull Subscription Properties](../view-and-modify-pull-subscription-properties.md) (Ver y modificar las propiedades de una suscripción de extracción).</span><span class="sxs-lookup"><span data-stu-id="16e47-105">For information about setting the mode when using this wizard, see [View and Modify Pull Subscription Properties](../view-and-modify-pull-subscription-properties.md).</span></span>  
  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="16e47-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="16e47-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="16e47-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="16e47-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="16e47-108">Puede conmutar por error desde actualización inmediata a actualización en cola en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="16e47-108">You can fail over from immediate to queued updating at any time.</span></span> <span data-ttu-id="16e47-109">No obstante, una vez hecho esto, no se puede volver a actualización inmediata hasta que el suscriptor y el publicador estén conectados y el Agente de lectura de cola haya aplicado todos los mensajes pendientes en la cola al publicador.</span><span class="sxs-lookup"><span data-stu-id="16e47-109">After you do, however, you cannot return to immediate updating until the Subscriber and Publisher are connected and the Queue Reader Agent has applied all pending messages in the queue to the Publisher.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="16e47-110">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="16e47-110">Recommendations</span></span>  
  
-   <span data-ttu-id="16e47-111">Cuando una suscripción de actualización a una publicación transaccional admite la conmutación por error de un modo de actualización a otro, se puede cambiar entre modos de actualización mediante programación para controlar las situaciones en que la conectividad cambia durante un breve período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="16e47-111">When an updating subscription to a transactional publication supports failover from one updating mode to another, you can programmatically switch update modes to handle situations when connectivity changes for a short period of time.</span></span> <span data-ttu-id="16e47-112">Se puede establecer el modo de actualización mediante programación y a petición con procedimientos almacenados de replicación.</span><span class="sxs-lookup"><span data-stu-id="16e47-112">The update mode can be set programmatically and on demand using replication stored procedures.</span></span> <span data-ttu-id="16e47-113">Para más información, consulte [Updatable Subscriptions for Transactional Replication](../transactional/updatable-subscriptions-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="16e47-113">For more information, see [Updatable Subscriptions for Transactional Replication](../transactional/updatable-subscriptions-for-transactional-replication.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="16e47-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="16e47-114">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16e47-115">Para cambiar el modo de actualización después de crear la suscripción, debe establecer la propiedad **update_mode** en **failover** (que permite cambiar de la actualización inmediata a la actualización en cola) o **queued failover** (que permite cambiar de la actualización en cola a la actualización inmediata) al crear la suscripción.</span><span class="sxs-lookup"><span data-stu-id="16e47-115">To change the update mode after the subscription is created, the **update_mode** property must be set to **failover** (which allows a switch from immediate updating to queued updating) or **queued failover** (which allows a switch from queued updating to immediate updating) when the subscription is created.</span></span> <span data-ttu-id="16e47-116">Estas propiedades se establecen automáticamente en el Asistente para nuevas suscripciones.</span><span class="sxs-lookup"><span data-stu-id="16e47-116">These properties are set automatically in the New Subscription Wizard.</span></span>  
  
#### <a name="to-set-the-updating-mode-for-a-push-subscription"></a><span data-ttu-id="16e47-117">Para establecer el modo de actualización para una suscripción de inserción</span><span class="sxs-lookup"><span data-stu-id="16e47-117">To set the updating mode for a push subscription</span></span>  
  
1.  <span data-ttu-id="16e47-118">Conéctese al suscriptor en [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]y expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="16e47-118">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="16e47-119">Expanda la carpeta **Replicación** y, a continuación, la carpeta **Suscripciones locales**.</span><span class="sxs-lookup"><span data-stu-id="16e47-119">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="16e47-120">Haga clic con el botón secundario en la suscripción para la que desea establecer el modo de actualización y, a continuación, haga clic en **Establecer método de actualización**.</span><span class="sxs-lookup"><span data-stu-id="16e47-120">Right-click the subscription for which you want to set the update mode, and then click **Set Update Method**.</span></span>  
  
4.  <span data-ttu-id="16e47-121">En el cuadro de diálogo **Establecer método de actualización: \<Subscriber>: \<SubscriptionDatabase>** , seleccione **Actualización inmediata** o **Actualización en cola**.</span><span class="sxs-lookup"><span data-stu-id="16e47-121">In the **Set Update Method - \<Subscriber>: \<SubscriptionDatabase>** dialog box, select **Immediate updating** or **Queued updating**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-set-the-updating-mode-for-a-pull-subscription"></a><span data-ttu-id="16e47-122">Para establecer el modo de actualización para una suscripción de extracción</span><span class="sxs-lookup"><span data-stu-id="16e47-122">To set the updating mode for a pull subscription</span></span>  
  
1.  <span data-ttu-id="16e47-123">En el cuadro de diálogo **Propiedades de suscripción: \<Publisher>: \<PublicationDatabase>** , seleccione el valor **Replicar cambios inmediatamente** o **Poner en cola cambios** para la opción **Método de actualización del suscriptor**.</span><span class="sxs-lookup"><span data-stu-id="16e47-123">In the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, select a value of **Immediately replicate changes** or **Queue changes** for the **Subscriber update method** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="16e47-124">Para obtener más información sobre cómo acceder al cuadro de diálogo **Propiedades de la suscripción: \<Publisher>: \<PublicationDatabase>** , vea [Ver y modificar las propiedades de una suscripción de extracción](../view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="16e47-124">For more information about accessing the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, see [View and Modify Pull Subscription Properties](../view-and-modify-pull-subscription-properties.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="16e47-125">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="16e47-125">Using Transact-SQL</span></span>  
  
#### <a name="to-switch-between-update-modes"></a><span data-ttu-id="16e47-126">Para cambiar entre modos de actualización</span><span class="sxs-lookup"><span data-stu-id="16e47-126">To switch between update modes</span></span>  
  
1.  <span data-ttu-id="16e47-127">Compruebe que la suscripción admite la conmutación por error ejecutando [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql) para una suscripción de extracción o [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) para una suscripción de inserción.</span><span class="sxs-lookup"><span data-stu-id="16e47-127">Verify that the subscription supports failover by executing [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql) for a pull subscription or [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) for a push subscription.</span></span> <span data-ttu-id="16e47-128">Si el valor del **modo de la actualización** en el conjunto de resultados es **3** o **4**, se admite la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="16e47-128">If the value of **update mode** in the result set is **3** or **4**, failover is supported.</span></span>  
  
2.  <span data-ttu-id="16e47-129">En el publicador de la base de datos de suscripciones, ejecute [sp_setreplfailovermode](/sql/relational-databases/system-stored-procedures/sp-setreplfailovermode-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="16e47-129">At the Subscriber on the subscription database, execute [sp_setreplfailovermode](/sql/relational-databases/system-stored-procedures/sp-setreplfailovermode-transact-sql).</span></span> <span data-ttu-id="16e47-130">Especifique **@publisher** , **@publisher_db** , **@publication** y uno de los siguientes valores para **@failover_mode** :</span><span class="sxs-lookup"><span data-stu-id="16e47-130">Specify **@publisher**, **@publisher_db**, **@publication**, and one of the following values for **@failover_mode**:</span></span>  
  
    -   <span data-ttu-id="16e47-131">**queued** : conmutación por error a actualización en cola cuando se ha perdido la conectividad temporalmente.</span><span class="sxs-lookup"><span data-stu-id="16e47-131">**queued** - fail over to queued updating when connectivity has been temporarily lost.</span></span>  
  
    -   <span data-ttu-id="16e47-132">**immediate** : conmutación por error a actualización inmediata cuando se ha restaurado la conectividad.</span><span class="sxs-lookup"><span data-stu-id="16e47-132">**immediate** - fail over to immediate updating when connectivity has been restored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16e47-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="16e47-133">See Also</span></span>  
 [<span data-ttu-id="16e47-134">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="16e47-134">Updatable Subscriptions for Transactional Replication</span></span>](../transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
