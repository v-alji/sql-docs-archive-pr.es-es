---
title: Establecer el período de expiración para las suscripciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication], expiration
- expiration [SQL Server replication]
- retention periods [SQL Server replication]
- deactivating subscriptions
ms.assetid: 542f0613-5817-42d0-b841-fb2c94010665
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bc0ecb449af64b88cf3ded032c78c2e399dd4234
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673643"
---
# <a name="set-the-expiration-period-for-subscriptions"></a><span data-ttu-id="53dec-102">Establecer el período de expiración para las suscripciones</span><span class="sxs-lookup"><span data-stu-id="53dec-102">Set the Expiration Period for Subscriptions</span></span>
  <span data-ttu-id="53dec-103">En este tema se describe cómo establecer el período de expiración para las suscripciones en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53dec-103">This topic describes how to set the expiration period for subscriptions in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="53dec-104">El período de expiración de las suscripciones determina el tiempo que debe transcurrir antes de que una suscripción expire y se quite.</span><span class="sxs-lookup"><span data-stu-id="53dec-104">The expiration period for subscriptions determines the period of time before a subscription expires and is removed.</span></span> <span data-ttu-id="53dec-105">Para más información, consulte [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="53dec-105">For more information, see [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span></span>  
  
 <span data-ttu-id="53dec-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="53dec-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="53dec-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="53dec-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="53dec-108">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="53dec-108">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="53dec-109">**Para establecer el período de expiración para las suscripciones con:**</span><span class="sxs-lookup"><span data-stu-id="53dec-109">**To set the expiration period for subscriptions, using:**</span></span>  
  
     [<span data-ttu-id="53dec-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="53dec-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="53dec-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="53dec-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="53dec-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="53dec-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="53dec-113">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="53dec-113">Recommendations</span></span>  
  
-   <span data-ttu-id="53dec-114">El período de expiración de las suscripciones recibe también el nombre de *período de retención de la publicación*.</span><span class="sxs-lookup"><span data-stu-id="53dec-114">The subscription expiration period is also referred to as the *publication retention period*.</span></span> <span data-ttu-id="53dec-115">La limpieza de los metadatos de replicación de mezcla depende de este valor:</span><span class="sxs-lookup"><span data-stu-id="53dec-115">Cleanup of merge replication metadata is dependent on this setting:</span></span>  
  
    -   <span data-ttu-id="53dec-116">La replicación no puede limpiar metadatos en las bases de datos de suscripciones y publicaciones hasta que se haya alcanzado el período de retención.</span><span class="sxs-lookup"><span data-stu-id="53dec-116">Replication cannot clean up metadata in the publication and subscription databases until the retention period is reached.</span></span> <span data-ttu-id="53dec-117">Tenga cuidado al especificar un valor elevado para el período de retención, ya que puede afectar negativamente al rendimiento de la replicación.</span><span class="sxs-lookup"><span data-stu-id="53dec-117">Use caution in specifying a high value for the retention period, because it can negatively impact replication performance.</span></span> <span data-ttu-id="53dec-118">Se recomienda utilizar un valor bajo si puede prever con exactitud que todos los suscriptores se sincronizarán con regularidad dentro del período establecido.</span><span class="sxs-lookup"><span data-stu-id="53dec-118">It is recommended that you use a lower setting if you can reliably predict that all Subscribers will synchronize regularly within that time period.</span></span>  
  
         <span data-ttu-id="53dec-119">El período de retención de las publicaciones de combinación tiene un período de gracia de 24 horas para incluir a los suscriptores en diferentes zonas horarias.</span><span class="sxs-lookup"><span data-stu-id="53dec-119">The retention period for merge publications has a 24-hour grace period to accommodate Subscribers in different time zones.</span></span> <span data-ttu-id="53dec-120">Si, por ejemplo, se establece un período de retención de un día, el período de retención real será de 48 horas.</span><span class="sxs-lookup"><span data-stu-id="53dec-120">If, for example, you set a retention period of one day, the actual retention period is 48 hours.</span></span>  
  
    -   <span data-ttu-id="53dec-121">Es posible especificar que las suscripciones no expiren nunca, pero se recomienda encarecidamente no utilizar ese valor, ya que los metadatos no se podrían limpiar.</span><span class="sxs-lookup"><span data-stu-id="53dec-121">It is possible to specify that subscriptions never expire, but it is strongly recommended that you do not use this value, because metadata cannot be cleaned up.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="53dec-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="53dec-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="53dec-123">Establezca el período de expiración de las suscripciones en la página **General** del cuadro de diálogo **Propiedades de la publicación: \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="53dec-123">Set the expiration period for subscriptions on the **General** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="53dec-124">Para obtener más información sobre el acceso a este cuadro de diálogo, vea [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="53dec-124">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-set-the-expiration-period-for-subscriptions"></a><span data-ttu-id="53dec-125">Para establecer el período de expiración para las suscripciones</span><span class="sxs-lookup"><span data-stu-id="53dec-125">To set the expiration period for subscriptions</span></span>  
  
1.  <span data-ttu-id="53dec-126">En la sección **Expiración de la suscripción** de la página **General** del cuadro de diálogo **Propiedades de la publicación: \<Publication>** , especifique si las suscripciones deben caducar.</span><span class="sxs-lookup"><span data-stu-id="53dec-126">In the **Subscription expiration** section on the **General** page of the **Publication Properties - \<Publication>** dialog box, specify whether subscriptions should expire.</span></span>  
  
2.  <span data-ttu-id="53dec-127">Si deben expirar, especifique un período de expiración.</span><span class="sxs-lookup"><span data-stu-id="53dec-127">If they should expire, specify an expiration time period.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="53dec-128">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="53dec-128">Using Transact-SQL</span></span>  
 <span data-ttu-id="53dec-129">Puede utilizar los procedimientos almacenados de replicación para establecer este valor cuando se crea una publicación o para modificar este valor en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="53dec-129">You can use replication stored procedures to either set this value when a publication is created or modify this value at a later time.</span></span>  
  
#### <a name="to-set-the-expiration-period-for-a-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="53dec-130">Para establecer el período de expiración de una suscripción en una instantánea o una publicación transaccional</span><span class="sxs-lookup"><span data-stu-id="53dec-130">To set the expiration period for a subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="53dec-131">En el publicador, ejecute [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53dec-131">At the Publisher, execute [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span></span> <span data-ttu-id="53dec-132">Especifique el período de expiración deseado para la suscripción, en horas, para **\@retention**.</span><span class="sxs-lookup"><span data-stu-id="53dec-132">Specify the desired subscription expiration period, in hours, for **\@retention**.</span></span> <span data-ttu-id="53dec-133">El período de expiración predeterminado es 336 horas.</span><span class="sxs-lookup"><span data-stu-id="53dec-133">The default expiration period is 336 hours.</span></span> <span data-ttu-id="53dec-134">Para obtener más información, vea [Crear una suscripción](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="53dec-134">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-set-the-expiration-period-for-a-subscription-to-a-merge-publication"></a><span data-ttu-id="53dec-135">Para establecer el período de expiración de una suscripción en una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="53dec-135">To set the expiration period for a subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="53dec-136">En el publicador, ejecute [sp_addmergepublication](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53dec-136">At the Publisher, execute [sp_addmergepublication](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span></span> <span data-ttu-id="53dec-137">Especifique el valor deseado para el período de expiración de la suscripción en **\@retention**.</span><span class="sxs-lookup"><span data-stu-id="53dec-137">Specify the desired value for the subscription expiration period for **\@retention**.</span></span> <span data-ttu-id="53dec-138">Especifique las unidades en las que se expresa el período de expiración para **\@retention_period_unit**, que pueden ser unas de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="53dec-138">Specify the units in which the expiration period is expressed for **\@retention_period_unit**, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="53dec-139">**1** = semana</span><span class="sxs-lookup"><span data-stu-id="53dec-139">**1** = week</span></span>  
  
    -   <span data-ttu-id="53dec-140">**2** = mes</span><span class="sxs-lookup"><span data-stu-id="53dec-140">**2** = month</span></span>  
  
    -   <span data-ttu-id="53dec-141">**3** = año</span><span class="sxs-lookup"><span data-stu-id="53dec-141">**3** = year</span></span>  
  
     <span data-ttu-id="53dec-142">El período de expiración predeterminado es 14 días.</span><span class="sxs-lookup"><span data-stu-id="53dec-142">The default expiration period is 14 days.</span></span> <span data-ttu-id="53dec-143">Para obtener más información, vea [Crear una suscripción](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="53dec-143">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-change-the-expiration-period-for-a-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="53dec-144">Para cambiar el período de expiración de una suscripción a una instantánea o una publicación transaccional</span><span class="sxs-lookup"><span data-stu-id="53dec-144">To change the expiration period for a subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="53dec-145">En el publicador, ejecute [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53dec-145">At the Publisher, execute [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span></span> <span data-ttu-id="53dec-146">Especifique **retention** para **\@property** y el nuevo período de expiración de suscripción, en horas, para **\@value**.</span><span class="sxs-lookup"><span data-stu-id="53dec-146">Specify **retention** for **\@property** and the new subscription expiration period, in hours, for **\@value**.</span></span>  
  
#### <a name="to-change-the-expiration-period-for-a-subscription-to-a-merge-publication"></a><span data-ttu-id="53dec-147">Para cambiar el período de expiración de una suscripción a una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="53dec-147">To change the expiration period for a subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="53dec-148">En el publicador, ejecute [sp_helpmergepublication](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), y especifique **\@publication** y **\@publisher**.</span><span class="sxs-lookup"><span data-stu-id="53dec-148">At the Publisher, execute [sp_helpmergepublication](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), specifying **\@publication** and **\@publisher**.</span></span> <span data-ttu-id="53dec-149">Tenga en cuenta el valor de **retention_period_unit** en el conjunto de resultados, que puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="53dec-149">Note the value of **retention_period_unit** in the result set, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="53dec-150">**0** = día</span><span class="sxs-lookup"><span data-stu-id="53dec-150">**0** = day</span></span>  
  
    -   <span data-ttu-id="53dec-151">**1** = semana</span><span class="sxs-lookup"><span data-stu-id="53dec-151">**1** = week</span></span>  
  
    -   <span data-ttu-id="53dec-152">**2** = mes</span><span class="sxs-lookup"><span data-stu-id="53dec-152">**2** = month</span></span>  
  
    -   <span data-ttu-id="53dec-153">**3** = año</span><span class="sxs-lookup"><span data-stu-id="53dec-153">**3** = year</span></span>  
  
2.  <span data-ttu-id="53dec-154">En el publicador, ejecute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53dec-154">At the Publisher, execute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span> <span data-ttu-id="53dec-155">Especifique **retention** para **\@property** y el nuevo período de expiración de suscripción, como texto en función de la unidad de período de retención del paso 1, para **\@value**.</span><span class="sxs-lookup"><span data-stu-id="53dec-155">Specify **retention** for **\@property** and the new subscription expiration period, as text based on the retention period unit from step 1, for **\@value**.</span></span>  
  
3.  <span data-ttu-id="53dec-156">(Opcional) En el publicador, ejecute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53dec-156">(Optional) At the Publisher, execute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span> <span data-ttu-id="53dec-157">Especifique **retention_period_unit** para **\@property** y una nueva unidad para el período de expiración de la suscripción para **\@value**.</span><span class="sxs-lookup"><span data-stu-id="53dec-157">Specify **retention_period_unit** for **\@property** and a new unit for the subscription expiration period for **\@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53dec-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53dec-158">See Also</span></span>  
 <span data-ttu-id="53dec-159">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="53dec-159">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="53dec-160">Desactivación y expiración de la suscripción</span><span class="sxs-lookup"><span data-stu-id="53dec-160">Subscription Expiration and Deactivation</span></span>](../subscription-expiration-and-deactivation.md)  
  
  
