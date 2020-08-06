---
title: Estrategias para hacer copias de seguridad y restaurar la replicación de mezcla | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server replication], merge replication
- backups [SQL Server replication], merge replication
- restoring [SQL Server replication], merge replication
- merge replication [SQL Server replication], backup and restore
ms.assetid: b8ae31c6-d76f-4dd7-8f46-17d023ca3eca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 45e3259d93af4735569fcb6b6a9c7b9eddd52730
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748084"
---
# <a name="strategies-for-backing-up-and-restoring-merge-replication"></a><span data-ttu-id="33360-102">Estrategias para hacer copias de seguridad y restaurar la replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="33360-102">Strategies for Backing Up and Restoring Merge Replication</span></span>
  <span data-ttu-id="33360-103">Para la replicación de mezcla, cree periódicamente una copia de seguridad de las siguientes bases de datos:</span><span class="sxs-lookup"><span data-stu-id="33360-103">For merge replication, back up the following databases regularly:</span></span>  
  
-   <span data-ttu-id="33360-104">Base de datos de publicaciones en el publicador</span><span class="sxs-lookup"><span data-stu-id="33360-104">The publication database at the Publisher</span></span>   
-   <span data-ttu-id="33360-105">Base de datos de distribución en el distribuidor</span><span class="sxs-lookup"><span data-stu-id="33360-105">The distribution database at the Distributor</span></span>    
-   <span data-ttu-id="33360-106">Base de datos de suscripciones en el suscriptor</span><span class="sxs-lookup"><span data-stu-id="33360-106">The subscription database at each Subscriber</span></span>    
-   <span data-ttu-id="33360-107">Las bases de datos del sistema **maestra** y **msdb** en el publicador, el distribuidor y todos los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="33360-107">The **master** and **msdb** system databases at the Publisher, Distributor and all Subscribers.</span></span> <span data-ttu-id="33360-108">La copia de seguridad de cada una de estas bases de datos debe realizarse al mismo tiempo que la de las otras y la base de datos de replicación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="33360-108">These databases should be backed up at the same time as each other and the relevant replication database.</span></span> <span data-ttu-id="33360-109">Por ejemplo, cree la copia de seguridad de las bases de datos **master** y **msdb** en el publicador al mismo tiempo que crea la copia de seguridad de la base de datos de publicaciones.</span><span class="sxs-lookup"><span data-stu-id="33360-109">For example, back up the **master** and **msdb** databases at the Publisher at the same time you back up the publication database.</span></span> <span data-ttu-id="33360-110">Al restaurar la base de datos de publicaciones, asegúrese de que las bases de datos **master** y **msdb** sean coherentes con la base de datos de publicaciones en términos de configuración general y configuración de la replicación.</span><span class="sxs-lookup"><span data-stu-id="33360-110">If the publication database is restored, ensure that the **master** and **msdb** database are consistent with the publication database in terms of replication configuration and settings.</span></span>  
  
 <span data-ttu-id="33360-111">Si realiza regularmente copias de seguridad de registros, éstas deben capturar todos los cambios relacionados con la replicación.</span><span class="sxs-lookup"><span data-stu-id="33360-111">If you perform regular log backups, any replication-related changes should be captured in the log backups.</span></span> <span data-ttu-id="33360-112">Si no se realizan copias de seguridad de registros, debe realizarse una copia de seguridad siempre que se cambie un valor importante en la replicación.</span><span class="sxs-lookup"><span data-stu-id="33360-112">If you don't perform log backups, a backup should be performed whenever a setting relevant to replication is changed.</span></span> <span data-ttu-id="33360-113">Para más información, vea [Common Actions Requiring an Updated Backup](common-actions-requiring-an-updated-backup.md).</span><span class="sxs-lookup"><span data-stu-id="33360-113">For more information, see [Common Actions Requiring an Updated Backup](common-actions-requiring-an-updated-backup.md).</span></span>  
  
 <span data-ttu-id="33360-114">Elija uno de los siguientes métodos para crear copias de seguridad y restaurar la base de datos de publicaciones; después, siga las recomendaciones para la base de datos de distribución y las bases de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="33360-114">Choose one of the approaches detailed below for backing up and restoring the publication database, and then follow the recommendations listed for the distribution database and subscription databases.</span></span>  
  
## <a name="backing-up-and-restoring-the-publication-database"></a><span data-ttu-id="33360-115">Realizar copias de seguridad y restaurar la base de datos de publicaciones</span><span class="sxs-lookup"><span data-stu-id="33360-115">Backing Up and Restoring the Publication Database</span></span>  
 <span data-ttu-id="33360-116">Hay dos métodos para restaurar una base de datos de publicaciones de combinación.</span><span class="sxs-lookup"><span data-stu-id="33360-116">There are two approaches to restoring a merge publication database.</span></span> <span data-ttu-id="33360-117">Después de restaurar la base de datos de publicaciones a partir de una copia de seguridad, debe:</span><span class="sxs-lookup"><span data-stu-id="33360-117">After restoring the publication database from a backup, you should either:</span></span>  
  
-   <span data-ttu-id="33360-118">Sincronizar la base de datos de publicaciones con una base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="33360-118">Synchronize the publication database with a subscription database.</span></span>  
  
-   <span data-ttu-id="33360-119">Reinicializar todas las suscripciones a las publicaciones en la base de datos de publicaciones.</span><span class="sxs-lookup"><span data-stu-id="33360-119">Reinitialize all subscriptions to the publications in the publication database.</span></span>  
  
 <span data-ttu-id="33360-120">Cualquiera de estos métodos garantiza la sincronización del publicador y de todos los suscriptores después de la restauración.</span><span class="sxs-lookup"><span data-stu-id="33360-120">Using either of these methods ensures that after a restore is performed, the Publisher and all Subscribers are synchronized.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33360-121">Si alguna tabla contiene columnas de identidad, debe asegurarse de asignar los intervalos de identidad correctos después de una restauración.</span><span class="sxs-lookup"><span data-stu-id="33360-121">If any tables contain identity columns, you must ensure the correct identity ranges are assigned after a restore.</span></span> <span data-ttu-id="33360-122">Para más información, vea [Replicar columnas de identidad](../publish/replicate-identity-columns.md).</span><span class="sxs-lookup"><span data-stu-id="33360-122">For more information, see [Replicate Identity Columns](../publish/replicate-identity-columns.md).</span></span>  
  
### <a name="synchronizing-the-publication-database"></a><span data-ttu-id="33360-123">Sincronizar la base de datos de publicaciones</span><span class="sxs-lookup"><span data-stu-id="33360-123">Synchronizing the Publication Database</span></span>  
 <span data-ttu-id="33360-124">La sincronización de una base de datos de publicaciones con una base de datos de suscripciones permite cargar desde una o más bases de datos de suscripciones los cambios realizados previamente en la base de datos de publicaciones que no están representados en la copia de seguridad restaurada.</span><span class="sxs-lookup"><span data-stu-id="33360-124">Synchronizing a publication database with a subscription database allows you to upload from one or more subscription databases those changes made previously in the publication database, but not represented in the restored backup.</span></span> <span data-ttu-id="33360-125">Los datos que se pueden cargar dependen de la forma en que se filtra una publicación:</span><span class="sxs-lookup"><span data-stu-id="33360-125">The data that can be uploaded depends on the way in which a publication is filtered:</span></span>  
  
-   <span data-ttu-id="33360-126">Si la publicación no está filtrada, debe poder actualizar la base de datos de publicaciones sincronizándola con el suscriptor más actualizado.</span><span class="sxs-lookup"><span data-stu-id="33360-126">If the publication is not filtered, you should be able to bring the publication database up-to-date by synchronizing with the most up-to-date Subscriber.</span></span>  
  
-   <span data-ttu-id="33360-127">Si la publicación está filtrada, es posible que no pueda actualizar la base de datos de publicaciones.</span><span class="sxs-lookup"><span data-stu-id="33360-127">If the publication is filtered, you might not be able to bring the publication database up-to-date.</span></span> <span data-ttu-id="33360-128">Considere una tabla dividida de forma que cada suscripción reciba únicamente datos de clientes de una región: norte, este, sur y oeste.</span><span class="sxs-lookup"><span data-stu-id="33360-128">Consider a table that is partitioned such that each subscription receives customer data only for a single region: North, East, South, and West.</span></span> <span data-ttu-id="33360-129">Si hay al menos un suscriptor para cada partición de datos, al sincronizar cada partición con un suscriptor se debería actualizar la base de datos de publicaciones.</span><span class="sxs-lookup"><span data-stu-id="33360-129">If there is at least one Subscriber for each partition of data, synchronizing with a Subscriber for each partition should bring the publication database up-to-date.</span></span> <span data-ttu-id="33360-130">Sin embargo, si los datos de la partición oeste, por ejemplo, no se han replicado en ningún suscriptor, no se podrán actualizar estos datos en el publicador.</span><span class="sxs-lookup"><span data-stu-id="33360-130">However, if data in the West partition, for example, was not replicated to any Subscribers, this data at the Publisher cannot be brought up-to-date.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="33360-131">La sincronización de una base de datos de publicaciones con una base de datos de suscripciones puede dar como resultado la restauración de las tablas publicadas hasta un momento más reciente que el de las otras tablas no publicadas restauradas de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="33360-131">Synchronizing a publication database with a subscription database can result in published tables being restored to a point in time that is more recent than the point in time of other non-published tables restored from the backup.</span></span>  
  
 <span data-ttu-id="33360-132">Si se sincroniza con un suscriptor que ejecute una versión de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] anterior a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], la suscripción no puede ser anónima, sino que debe ser una suscripción de cliente o de servidor (llamadas suscripciones locales y suscripciones globales en versiones anteriores).</span><span class="sxs-lookup"><span data-stu-id="33360-132">If you synchronize with a Subscriber that is running a version of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] prior to [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the subscription cannot be anonymous; it must be a client subscription or server subscription (referred to as local subscriptions and global subscriptions in previous releases).</span></span>  
  
 <span data-ttu-id="33360-133">Para sincronizar una suscripción de inserción, vea [Synchronize a Push Subscription](../synchronize-a-push-subscription.md) y [Synchronize a Pull Subscription](../synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="33360-133">To synchronize a subscription, see [Synchronize a Push Subscription](../synchronize-a-push-subscription.md) and [Synchronize a Pull Subscription](../synchronize-a-pull-subscription.md).</span></span>  
  
### <a name="reinitializing-all-subscriptions"></a><span data-ttu-id="33360-134">Reinicializar todas las suscripciones</span><span class="sxs-lookup"><span data-stu-id="33360-134">Reinitializing all Subscriptions</span></span>  
 <span data-ttu-id="33360-135">La reinicialización de todas las suscripciones garantiza que el estado de todos los suscriptores sea coherente con la base de datos de publicaciones restaurada.</span><span class="sxs-lookup"><span data-stu-id="33360-135">Reinitializing all subscriptions ensures all Subscribers are in a state consistent with the restored publication database.</span></span> <span data-ttu-id="33360-136">Este enfoque debe utilizarse si desea restaurar una topología completa a su estado anterior, representado por la copia de seguridad de una base de datos de publicaciones determinada.</span><span class="sxs-lookup"><span data-stu-id="33360-136">This approach should be used if you want to return an entire topology to the previous state represented by a given publication database backup.</span></span> <span data-ttu-id="33360-137">Por ejemplo, puede reinicializar todas las suscripciones si desea restaurar una base de datos a un momento anterior como un mecanismo para recuperarse de una operación por lotes realizada incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="33360-137">For example, you might want to reinitialize all subscriptions if you are restoring a publication database to an earlier point in time as a mechanism to recover from an erroneously performed batch operation.</span></span>  
  
 <span data-ttu-id="33360-138">Si elige esta opción, genere una nueva instantánea para entregar a los suscriptores reinicializados inmediatamente después de restaurar la base de datos de publicaciones.</span><span class="sxs-lookup"><span data-stu-id="33360-138">If you choose this option, generate a new snapshot for delivery to reinitialized Subscribers immediately after restoring your publication database.</span></span>  
  
 <span data-ttu-id="33360-139">Para reinicializar una suscripción, vea [Reinitialize a Subscription](../reinitialize-a-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="33360-139">To reinitialize a subscription, see [Reinitialize a Subscription](../reinitialize-a-subscription.md).</span></span>  
  
 <span data-ttu-id="33360-140">Para crear y aplicar una instantánea, vea [Create y Apply the Initial Snapshot](../create-and-apply-the-initial-snapshot.md) y [Create a Snapshot for a Merge Publication with Parameterized Filters](../create-a-snapshot-for-a-merge-publication-with-parameterized-filters.md).</span><span class="sxs-lookup"><span data-stu-id="33360-140">To create and apply a snapshot, see [Create and Apply the Initial Snapshot](../create-and-apply-the-initial-snapshot.md) and [Create a Snapshot for a Merge Publication with Parameterized Filters](../create-a-snapshot-for-a-merge-publication-with-parameterized-filters.md).</span></span>  
  
## <a name="backing-up-and-restoring-the-distribution-database"></a><span data-ttu-id="33360-141">Realizar copias de seguridad y restaurar la base de datos de distribución</span><span class="sxs-lookup"><span data-stu-id="33360-141">Backing Up and Restoring the Distribution Database</span></span>  
 <span data-ttu-id="33360-142">Con la replicación de mezcla, se deben crear periódicamente copias de seguridad de la base de datos de distribución, que se pueden restaurar sin ningún tipo de consideraciones especiales, siempre que la copia de seguridad utilizada no sea más antigua que el menor período de retención de todas las publicaciones que utilizan el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="33360-142">With merge replication, the distribution database should be backed up regularly, and can be restored without any special considerations as long as the backup used is no older than the shortest retention period of all publications that use the Distributor.</span></span> <span data-ttu-id="33360-143">Por ejemplo, si hay tres publicaciones con períodos de retención de 10, 20 y 30 días respectivamente, la copia de seguridad que deberá utilizarse para restaurar la base de datos no debe tener más de 10 días.</span><span class="sxs-lookup"><span data-stu-id="33360-143">For example, if there are three publications with retention periods of 10, 20, and 30 days, respectively, the backup used to restore the database should not be more than 10 days old.</span></span> <span data-ttu-id="33360-144">La base de datos de distribución tiene un rol limitado en la replicación de mezcla: no almacena ningún dato utilizado en el seguimiento de cambios y no almacena temporalmente los cambios de la replicación de mezcla que se enviarán a las bases de datos de suscripciones (como ocurre con la replicación transaccional).</span><span class="sxs-lookup"><span data-stu-id="33360-144">The distribution database has a limited role in merge replication: it does not store any data used in change tracking and it does not provide temporary storage of merge replication changes to be forwarded to subscription databases (as it does in transactional replication).</span></span>  
  
## <a name="backing-up-and-restoring-a-subscription-database"></a><span data-ttu-id="33360-145">Realizar copias de seguridad y restaurar la base de datos de suscripciones</span><span class="sxs-lookup"><span data-stu-id="33360-145">Backing Up and Restoring a Subscription Database</span></span>  
 <span data-ttu-id="33360-146">Para garantizar la recuperación correcta de una base de datos de suscripciones, los suscriptores deben sincronizarse con el publicador antes de crear la copia de seguridad de la base de datos de suscripciones y después de restaurar la base de datos de suscripciones:</span><span class="sxs-lookup"><span data-stu-id="33360-146">To ensure successful recovery of a subscription database, Subscribers should synchronize with the Publisher before the subscription database is backed up; they should also synchronize after the subscription database is restored:</span></span>  
  
-   <span data-ttu-id="33360-147">La sincronización con el publicador antes de crear la copia de seguridad de la base de datos de suscripciones ayuda a garantizar que si se restaura un suscriptor a partir de la copia de seguridad, la suscripción seguirá estando dentro del período de retención de la publicación.</span><span class="sxs-lookup"><span data-stu-id="33360-147">Synchronizing with the Publisher before a subscription database backup helps ensure that if a Subscriber is restored from backup, the subscription is still within the publication retention period.</span></span> <span data-ttu-id="33360-148">Por ejemplo, imagine una publicación con un período de retención de 10 días.</span><span class="sxs-lookup"><span data-stu-id="33360-148">For example, assume a publication with a retention period of 10 days.</span></span> <span data-ttu-id="33360-149">Suponga que la última sincronización se realizó hace 8 días y que ahora se efectúa la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="33360-149">The last synchronization was 8 days ago, and now the backup is performed.</span></span> <span data-ttu-id="33360-150">Si la copia de seguridad se restaura 4 días más tarde, ya habrán transcurrido 12 días desde la última sincronización, un período superior al de retención.</span><span class="sxs-lookup"><span data-stu-id="33360-150">If the backup is restored 4 days later, the last synchronization will have occurred 12 days ago, which is past the retention period.</span></span> <span data-ttu-id="33360-151">En este caso, será necesario reinicializar el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="33360-151">In this case, you would have to reinitialize the Subscriber.</span></span> <span data-ttu-id="33360-152">Si el suscriptor se hubiera sincronizado antes de realizar la copia de seguridad, la base de datos de suscripciones todavía estaría dentro del período de retención.</span><span class="sxs-lookup"><span data-stu-id="33360-152">If the Subscriber had synchronized before the backup, the subscription database would be within the retention period.</span></span>  
  
     <span data-ttu-id="33360-153">La copia de seguridad no debe ser anterior al menor período de retención de todas las publicaciones a las que se suscribe el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="33360-153">The backup should be no older than the shortest retention period of all publications to which the Subscriber subscribes.</span></span> <span data-ttu-id="33360-154">Por ejemplo, si un suscriptor se suscribe a tres publicaciones cuyos períodos de retención son 12, 20 y 30 días respectivamente, la copia de seguridad que deberá utilizarse para restaurar la base de datos no debería tener más de 10 días.</span><span class="sxs-lookup"><span data-stu-id="33360-154">For example, if a Subscriber subscribes to three publications with retention periods of 10, 20, and 30 days, respectively, the backup used to restore the database should not be more than 10 days old.</span></span>  
  
-   <span data-ttu-id="33360-155">Sincronizar la base de datos de suscripciones con cada una de sus publicaciones después de una restauración garantiza que el suscriptor se actualice con todos los cambios presentes en el publicador.</span><span class="sxs-lookup"><span data-stu-id="33360-155">Synchronizing the subscription database with each of its publications following a restore ensures that the Subscriber is up to date with all changes at the Publisher.</span></span>  
  
 <span data-ttu-id="33360-156">Para establecer el período de retención de publicación, vea [Set the Expiration Period for Subscriptions](../publish/set-the-expiration-period-for-subscriptions.md) (Establecer el período de expiración para las suscripciones).</span><span class="sxs-lookup"><span data-stu-id="33360-156">To set the publication retention period, see [Set the Expiration Period for Subscriptions](../publish/set-the-expiration-period-for-subscriptions.md).</span></span>  
  
 <span data-ttu-id="33360-157">Para sincronizar una suscripción de inserción, vea [Synchronize a Push Subscription](../synchronize-a-push-subscription.md) y [Synchronize a Pull Subscription](../synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="33360-157">To synchronize a subscription, see [Synchronize a Push Subscription](../synchronize-a-push-subscription.md) and [Synchronize a Pull Subscription](../synchronize-a-pull-subscription.md).</span></span>  
  
## <a name="backing-up-and-restoring-a-republishing-database"></a><span data-ttu-id="33360-158">Realizar copias de seguridad y restaurar una base de datos de republicaciones</span><span class="sxs-lookup"><span data-stu-id="33360-158">Backing Up and Restoring a Republishing Database</span></span>  
 <span data-ttu-id="33360-159">Cuando una base de datos se suscribe a datos de un publicador y, a su vez, publica esos mismos datos en otras bases de datos de suscripciones se denomina base de datos de republicaciones.</span><span class="sxs-lookup"><span data-stu-id="33360-159">When a database subscribes to data from a Publisher and in turn publishes that same data to other subscription databases, it is referred to as a republishing database.</span></span> <span data-ttu-id="33360-160">Al restaurar una base de datos de republicaciones, siga las directrices descritas en las secciones "Realizar copias de seguridad y restaurar la base de datos de publicaciones" y "Realizar copias de seguridad y restaurar la base de datos de suscripciones" de este tema.</span><span class="sxs-lookup"><span data-stu-id="33360-160">When restoring a republishing database, follow the guidelines described in "Backing Up and Restoring a Publication Database" and "Backing Up and Restoring a Subscription Database" in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33360-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33360-161">See Also</span></span>  
 <span data-ttu-id="33360-162">[Realizar copias de seguridad y restaurar bases de datos de SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="33360-162">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="33360-163">Hacer copias de seguridad y restaurar bases de datos replicadas</span><span class="sxs-lookup"><span data-stu-id="33360-163">Back Up and Restore Replicated Databases</span></span>](back-up-and-restore-replicated-databases.md)  
  
  