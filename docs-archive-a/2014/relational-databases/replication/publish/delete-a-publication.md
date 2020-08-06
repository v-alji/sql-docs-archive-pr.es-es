---
title: Eliminación de una publicación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- removing publications
- publications [SQL Server replication], deleting
- articles [SQL Server replication], deleting
- deleting publications
ms.assetid: 408a1360-12ee-4896-ac94-482ae839593b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d2b39a326d59333868b4f8015eb9a2e59d59e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750678"
---
# <a name="delete-a-publication"></a><span data-ttu-id="c1da9-102">Eliminar una publicación</span><span class="sxs-lookup"><span data-stu-id="c1da9-102">Delete a Publication</span></span>
  <span data-ttu-id="c1da9-103">En este tema se describe cómo eliminar una publicación en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="c1da9-103">This topic describes how to delete a publication in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="c1da9-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="c1da9-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c1da9-105">**Para eliminar una publicación con:**</span><span class="sxs-lookup"><span data-stu-id="c1da9-105">**To delete a publication, using:**</span></span>  
  
     [<span data-ttu-id="c1da9-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1da9-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c1da9-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1da9-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="c1da9-108">Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="c1da9-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c1da9-109">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1da9-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="c1da9-110">Elimine publicaciones de la carpeta **Publicaciones locales** en [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1da9-110">Delete publications from the **Local Publications** folder in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-delete-a-publication"></a><span data-ttu-id="c1da9-111">Para eliminar una publicación</span><span class="sxs-lookup"><span data-stu-id="c1da9-111">To delete a publication</span></span>  
  
1.  <span data-ttu-id="c1da9-112">Conéctese al publicador en [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]y luego expanda el nodo del servidor.</span><span class="sxs-lookup"><span data-stu-id="c1da9-112">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="c1da9-113">Expanda la carpeta **Replicación** y, a continuación, expanda la carpeta **Publicaciones locales** .</span><span class="sxs-lookup"><span data-stu-id="c1da9-113">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="c1da9-114">Haga clic con el botón secundario en la publicación que desea eliminar y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c1da9-114">Right-click the publication you want to delete, and then click **Delete**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c1da9-115">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1da9-115">Using Transact-SQL</span></span>  
 <span data-ttu-id="c1da9-116">Las publicaciones pueden eliminarse mediante programación con procedimientos almacenados de replicación.</span><span class="sxs-lookup"><span data-stu-id="c1da9-116">Publications can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="c1da9-117">Los procedimientos almacenados que use dependen del tipo de publicación que se elimina.</span><span class="sxs-lookup"><span data-stu-id="c1da9-117">The stored procedures that you use depend on the type of publication being deleted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1da9-118">Al eliminar una publicación, no se quitan los objetos publicados de la base de datos de publicación ni los objetos correspondientes de la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="c1da9-118">Deleting a publication does not remove published objects from the publication database or the corresponding objects from the subscription database.</span></span> <span data-ttu-id="c1da9-119">Si es necesario, use el comando `DROP <object>` para quitar estos objetos manualmente.</span><span class="sxs-lookup"><span data-stu-id="c1da9-119">Use the `DROP <object>` command to manually remove these objects if necessary.</span></span>  
  
#### <a name="to-delete-a-snapshot-or-transactional-publication"></a><span data-ttu-id="c1da9-120">Para eliminar una publicación transaccional o de instantáneas</span><span class="sxs-lookup"><span data-stu-id="c1da9-120">To delete a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="c1da9-121">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c1da9-121">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="c1da9-122">Para eliminar una publicación, ejecute [sp_droppublication](/sql/relational-databases/system-stored-procedures/sp-droppublication-transact-sql) en la base de datos de publicación del publicador.</span><span class="sxs-lookup"><span data-stu-id="c1da9-122">To delete a single publication, execute [sp_droppublication](/sql/relational-databases/system-stored-procedures/sp-droppublication-transact-sql) at the Publisher on the publication database.</span></span>  
  
    -   <span data-ttu-id="c1da9-123">Para eliminar todas las publicaciones de una base de datos publicada y quitar todos sus objetos de replicación, ejecute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) en el publicador.</span><span class="sxs-lookup"><span data-stu-id="c1da9-123">To delete all publications in and remove all replication objects from a published database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) at the Publisher.</span></span> <span data-ttu-id="c1da9-124">Especifique un valor de `tran` para \*\* \@ tipo\*\*.</span><span class="sxs-lookup"><span data-stu-id="c1da9-124">Specify a value of `tran` for **\@type**.</span></span> <span data-ttu-id="c1da9-125">(Opcional) Si no se puede tener acceso al distribuidor, o bien si el estado de la base de datos es sospechoso o está sin conexión, especifique un valor de **1** para **\@force**.</span><span class="sxs-lookup"><span data-stu-id="c1da9-125">(Optional) If the Distributor cannot be accessed or if the status of the database is suspect or offline, specify a value of **1** for **\@force**.</span></span> <span data-ttu-id="c1da9-126">(Opcional) Especifique el nombre de la base de datos para **\@dbname** si [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) no se ejecuta en la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="c1da9-126">(Optional) Specify the name of the database for **\@dbname** if [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) is not executed on the publication database.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="c1da9-127">Especificar un valor de **1** para **\@force** puede dejar objetos de publicación relacionados con la replicación en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c1da9-127">Specifying a value of **1** for **\@force** may leave replication-related publishing objects in the database.</span></span>  
  
2.  <span data-ttu-id="c1da9-128">(Opcional) Si esta base de datos no tiene otras publicaciones, ejecute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) para deshabilitar la publicación de la base de datos actual mediante la replicación transaccional o de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="c1da9-128">(Optional) If this database has no other publications, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) to disable publication of the current database using snapshot or transactional replication.</span></span>  
  
3.  <span data-ttu-id="c1da9-129">(Opcional) En la base de datos de suscripciones del suscriptor, ejecute [sp_subscription_cleanup](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) para quitar los metadatos de replicación restantes en la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="c1da9-129">(Optional) At the Subscriber on the subscription database, execute [sp_subscription_cleanup](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) to remove any remaining replication metadata in the subscription database.</span></span>  
  
#### <a name="to-delete-a-merge-publication"></a><span data-ttu-id="c1da9-130">Para eliminar una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="c1da9-130">To delete a merge publication</span></span>  
  
1.  <span data-ttu-id="c1da9-131">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c1da9-131">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="c1da9-132">Para eliminar una publicación, ejecute [sp_dropmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergepublication-transact-sql) en la base de datos de publicación del publicador.</span><span class="sxs-lookup"><span data-stu-id="c1da9-132">To delete a single publication, execute [sp_dropmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergepublication-transact-sql) at the Publisher on the publication database.</span></span>  
  
    -   <span data-ttu-id="c1da9-133">Para eliminar todas las publicaciones de una base de datos publicada y quitar todos sus objetos de replicación, ejecute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) en el publicador.</span><span class="sxs-lookup"><span data-stu-id="c1da9-133">To delete all publications in and remove all replication objects from a published database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) at the Publisher.</span></span> <span data-ttu-id="c1da9-134">Especifique un valor de `merge` para \*\* \@ tipo\*\*.</span><span class="sxs-lookup"><span data-stu-id="c1da9-134">Specify a value of `merge` for **\@type**.</span></span> <span data-ttu-id="c1da9-135">(Opcional) Si no se puede tener acceso al distribuidor, o bien si el estado de la base de datos es sospechoso o está sin conexión, especifique un valor de **1** para **\@force**.</span><span class="sxs-lookup"><span data-stu-id="c1da9-135">(Optional) If the Distributor cannot be accessed or if the status of the database is suspect or offline, specify a value of **1** for **\@force**.</span></span> <span data-ttu-id="c1da9-136">(Opcional) Especifique el nombre de la base de datos para **\@dbname** si [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) no se ejecuta en la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="c1da9-136">(Optional) Specify the name of the database for **\@dbname** if [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) is not executed on the publication database.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="c1da9-137">Especificar un valor de **1** para **\@force** puede dejar objetos de publicación relacionados con la replicación en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c1da9-137">Specifying a value of **1** for **\@force** may leave replication-related publishing objects in the database.</span></span>  
  
2.  <span data-ttu-id="c1da9-138">(Opcional) Si esta base de datos no tiene otras publicaciones, ejecute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) para deshabilitar la publicación de la base de datos actual con la replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="c1da9-138">(Optional) If this database has no other publications, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) to disable publication of the current database using merge replication.</span></span>  
  
3.  <span data-ttu-id="c1da9-139">(Opcional) En la base de datos de suscripciones del suscriptor, ejecute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql) para quitar los metadatos de replicación restantes en la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="c1da9-139">(Optional) At the Subscriber on the subscription database, execute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql) to remove any remaining replication metadata in the subscription database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="c1da9-140">Ejemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c1da9-140">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="c1da9-141">Este ejemplo muestra cómo quitar una publicación transaccional y deshabilitar la publicación transaccional para una base de datos.</span><span class="sxs-lookup"><span data-stu-id="c1da9-141">This example shows how to remove a transactional publication and disable transactional publishing for a database.</span></span> <span data-ttu-id="c1da9-142">Este ejemplo supone que se quitaron todas las suscripciones previamente.</span><span class="sxs-lookup"><span data-stu-id="c1da9-142">This example assumes that all subscriptions were previously removed.</span></span> <span data-ttu-id="c1da9-143">Para obtener más información, consulte [Delete a Pull Subscription](../delete-a-pull-subscription.md) o [Delete a Push Subscription](../delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="c1da9-143">For more information, see [Delete a Pull Subscription](../delete-a-pull-subscription.md) or [Delete a Push Subscription](../delete-a-push-subscription.md).</span></span>  
  
 [!code-sql[HowTo#sp_droppublication](../../../snippets/tsql/SQL15/replication/howto/tsql/droptranpub.sql#sp_droppublication)]  
  
 <span data-ttu-id="c1da9-144">Este ejemplo muestra cómo quitar una publicación de combinación y deshabilitar la publicación de combinación para una base de datos.</span><span class="sxs-lookup"><span data-stu-id="c1da9-144">This example shows how to remove a merge publication and disable merge publishing for a database.</span></span> <span data-ttu-id="c1da9-145">Este ejemplo supone que se quitaron todas las suscripciones previamente.</span><span class="sxs-lookup"><span data-stu-id="c1da9-145">This example assumes that all subscriptions were previously removed.</span></span> <span data-ttu-id="c1da9-146">Para obtener más información, consulte [Delete a Pull Subscription](../delete-a-pull-subscription.md) o [Delete a Push Subscription](../delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="c1da9-146">For more information, see [Delete a Pull Subscription](../delete-a-pull-subscription.md) or [Delete a Push Subscription](../delete-a-push-subscription.md).</span></span>  
  
 [!code-sql[HowTo#sp_dropmergepublication](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepub.sql#sp_dropmergepublication)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="c1da9-147">Uso de Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="c1da9-147">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="c1da9-148">Puede eliminar publicación mediante programación utilizando Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="c1da9-148">You can delete publications programmatically by using Replication Management Objects (RMO).</span></span> <span data-ttu-id="c1da9-149">Las clases RMO que utiliza para quitar una publicación dependen del tipo de publicación que quita.</span><span class="sxs-lookup"><span data-stu-id="c1da9-149">The RMO classes that you use to remove a publication depend on the type of publication you remove.</span></span>  
  
#### <a name="to-remove-a-snapshot-or-transactional-publication"></a><span data-ttu-id="c1da9-150">Para quitar una publicación transaccional o de instantáneas</span><span class="sxs-lookup"><span data-stu-id="c1da9-150">To remove a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="c1da9-151">Cree una conexión al publicador mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="c1da9-151">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="c1da9-152">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.TransPublication>.</span><span class="sxs-lookup"><span data-stu-id="c1da9-152">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPublication> class.</span></span>  
  
3.  <span data-ttu-id="c1da9-153">Establezca las propiedades <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> y <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> para la publicación y la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> en la conexión creada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="c1da9-153">Set the <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> and <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> properties for the publication, and set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="c1da9-154">Compruebe la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> para asegurarse de que la publicación existe.</span><span class="sxs-lookup"><span data-stu-id="c1da9-154">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the publication exists.</span></span> <span data-ttu-id="c1da9-155">Si el valor de esta propiedad es `false`, significa que las propiedades de la publicación del paso 3 se definieron incorrectamente, o bien que la publicación no existe.</span><span class="sxs-lookup"><span data-stu-id="c1da9-155">If the value of this property is `false`, either the publication properties in step 3 were defined incorrectly or the publication does not exist.</span></span>  
  
5.  <span data-ttu-id="c1da9-156">Llame al método <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="c1da9-156">Call the <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> method.</span></span>  
  
6.  <span data-ttu-id="c1da9-157">(Opcional) Si no existe ninguna otra publicación transaccional para esta base de datos, ésta se puede deshabilitar para la publicación transaccional del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="c1da9-157">(Optional) If no other transactional publications exist for this database, the database can be disabled for transactional publishing as follows:</span></span>  
  
    1.  <span data-ttu-id="c1da9-158">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.ReplicationDatabase>.</span><span class="sxs-lookup"><span data-stu-id="c1da9-158">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase> class.</span></span> <span data-ttu-id="c1da9-159">Establezca la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> en la instancia de <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del paso 1.</span><span class="sxs-lookup"><span data-stu-id="c1da9-159">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the instance of <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1.</span></span>  
  
    2.  <span data-ttu-id="c1da9-160">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="c1da9-160">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="c1da9-161">Si este método devuelve `false`, confirme que la base de datos existe.</span><span class="sxs-lookup"><span data-stu-id="c1da9-161">If this method returns `false`, confirm that the database exists.</span></span>  
  
    3.  <span data-ttu-id="c1da9-162">Establezca la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledTransPublishing%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="c1da9-162">Set the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledTransPublishing%2A> property to `false`.</span></span>  
  
    4.  <span data-ttu-id="c1da9-163">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="c1da9-163">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="c1da9-164">Cierre las conexiones.</span><span class="sxs-lookup"><span data-stu-id="c1da9-164">Close the connections.</span></span>  
  
#### <a name="to-remove-a-merge-publication"></a><span data-ttu-id="c1da9-165">Para quitar una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="c1da9-165">To remove a merge publication</span></span>  
  
1.  <span data-ttu-id="c1da9-166">Cree una conexión al publicador mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="c1da9-166">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="c1da9-167">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.MergePublication>.</span><span class="sxs-lookup"><span data-stu-id="c1da9-167">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePublication> class.</span></span>  
  
3.  <span data-ttu-id="c1da9-168">Establezca las propiedades <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> y <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> para la publicación y la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> en la conexión creada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="c1da9-168">Set the <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> and <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> properties for the publication, and set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="c1da9-169">Compruebe la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> para asegurarse de que la publicación existe.</span><span class="sxs-lookup"><span data-stu-id="c1da9-169">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the publication exists.</span></span> <span data-ttu-id="c1da9-170">Si el valor de esta propiedad es `false`, significa que las propiedades de la publicación del paso 3 se definieron incorrectamente, o bien que la publicación no existe.</span><span class="sxs-lookup"><span data-stu-id="c1da9-170">If the value of this property is `false`, either the publication properties in step 3 were defined incorrectly or the publication does not exist.</span></span>  
  
5.  <span data-ttu-id="c1da9-171">Llame al método <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="c1da9-171">Call the <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> method.</span></span>  
  
6.  <span data-ttu-id="c1da9-172">(Opcional) Si no existe ninguna otra publicación de combinación para esta base de datos, ésta se puede deshabilitar para la publicación de combinación del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="c1da9-172">(Optional) If no other merge publications exist for this database, the database can be disabled for merge publishing as follows:</span></span>  
  
    1.  <span data-ttu-id="c1da9-173">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.ReplicationDatabase>.</span><span class="sxs-lookup"><span data-stu-id="c1da9-173">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase> class.</span></span> <span data-ttu-id="c1da9-174">Establezca la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> en la instancia de <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del paso 1.</span><span class="sxs-lookup"><span data-stu-id="c1da9-174">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the instance of <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from Step 1.</span></span>  
  
    2.  <span data-ttu-id="c1da9-175">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="c1da9-175">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="c1da9-176">Si este método devuelve `false`, compruebe que la base de datos existe.</span><span class="sxs-lookup"><span data-stu-id="c1da9-176">If this method returns `false`, verify that the database exists.</span></span>  
  
    3.  <span data-ttu-id="c1da9-177">Establezca la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledMergePublishing%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="c1da9-177">Set the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledMergePublishing%2A> property to `false`.</span></span>  
  
    4.  <span data-ttu-id="c1da9-178">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="c1da9-178">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="c1da9-179">Cierre las conexiones.</span><span class="sxs-lookup"><span data-stu-id="c1da9-179">Close the connections.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="c1da9-180">Ejemplos (RMO)</span><span class="sxs-lookup"><span data-stu-id="c1da9-180">Examples (RMO)</span></span>  
 <span data-ttu-id="c1da9-181">En el siguiente ejemplo se elimina una publicación transaccional</span><span class="sxs-lookup"><span data-stu-id="c1da9-181">The following example deletes a transactional publication.</span></span> <span data-ttu-id="c1da9-182">Si no existe ninguna otra publicación transaccional para esta base de datos, también se deshabilita la publicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="c1da9-182">If no other transactional publications exist for this database, transactional publishing is also disabled.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropTranPub](../../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_droptranpub)]  
  
 [!code-vb[HowTo#rmo_vb_DropTranPub](../../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_droptranpub)]  
  
 <span data-ttu-id="c1da9-183">En el siguiente ejemplo se elimina una publicación de combinación.</span><span class="sxs-lookup"><span data-stu-id="c1da9-183">The following example deletes a merge publication.</span></span> <span data-ttu-id="c1da9-184">Si no existe ninguna otra publicación de combinación para esta base de datos, también se deshabilita la publicación de combinación.</span><span class="sxs-lookup"><span data-stu-id="c1da9-184">If no other merge publications exist for this database, merge publishing is also disabled.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropMergePub](../../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropmergepub)]  
  
 [!code-vb[HowTo#rmo_vb_DropMergePub](../../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropmergepub)]  
  
## <a name="see-also"></a><span data-ttu-id="c1da9-185">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1da9-185">See Also</span></span>  
 <span data-ttu-id="c1da9-186">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="c1da9-186">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="c1da9-187">Publicar datos y objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="c1da9-187">Publish Data and Database Objects</span></span>](publish-data-and-database-objects.md)  
  
  
