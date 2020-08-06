---
title: Deshabilitar la publicación y la distribución | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- disabling publishing
- publishing [SQL Server replication], disabling
- distribution disabling [SQL Server replication]
- removing replication
- replication [SQL Server], removing
- disabling replication
- disabling distribution
ms.assetid: 6d4a1474-4d13-4826-8be2-80050fafa8a5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8843dac310d1e023fe7ce63eded02c9e1bed3731
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663392"
---
# <a name="disable-publishing-and-distribution"></a><span data-ttu-id="a8804-102">Deshabilitar la publicación y la distribución</span><span class="sxs-lookup"><span data-stu-id="a8804-102">Disable Publishing and Distribution</span></span>
  <span data-ttu-id="a8804-103">En este tema se describe cómo deshabilitar la publicación y la distribución en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="a8804-103">This topic describes how to disable publishing and distribution in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="a8804-104">Puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8804-104">You can do the following:</span></span>  
  
-   <span data-ttu-id="a8804-105">Eliminar todas las bases de datos del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="a8804-105">Delete all distribution databases on the Distributor.</span></span>  
  
-   <span data-ttu-id="a8804-106">Deshabilitar todos los publicadores que utilizan el distribuidor y eliminar todas las publicaciones en esos publicadores.</span><span class="sxs-lookup"><span data-stu-id="a8804-106">Disable all Publishers that use the Distributor and delete all publications on those Publishers.</span></span>  
  
-   <span data-ttu-id="a8804-107">Eliminar todas las suscripciones a las publicaciones.</span><span class="sxs-lookup"><span data-stu-id="a8804-107">Delete all subscriptions to the publications.</span></span> <span data-ttu-id="a8804-108">Los datos de las bases de datos de publicaciones y de suscripciones no se eliminarán; sin embargo, pierden su relación de sincronización con todas las bases de datos de publicaciones.</span><span class="sxs-lookup"><span data-stu-id="a8804-108">Data in the publication and subscription databases will not be deleted; however, it loses its synchronization relationship to any publication databases.</span></span> <span data-ttu-id="a8804-109">Si desea eliminar los datos del suscriptor, debe hacerlo de forma manual.</span><span class="sxs-lookup"><span data-stu-id="a8804-109">If you want the data at the Subscriber to be deleted, you must delete it manually.</span></span>  
  
 <span data-ttu-id="a8804-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="a8804-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a8804-111">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="a8804-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a8804-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a8804-112">Prerequisites</span></span>](#Prerequisites)  
  
-   <span data-ttu-id="a8804-113">**Para deshabilitar la publicación y la distribución con:**</span><span class="sxs-lookup"><span data-stu-id="a8804-113">**To disable publishing and distribution, using:**</span></span>  
  
     [<span data-ttu-id="a8804-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a8804-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a8804-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a8804-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="a8804-116">Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="a8804-116">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a8804-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a8804-117">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a8804-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a8804-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="a8804-119">Para deshabilitar la publicación y la distribución, todas las bases de datos de distribución y de publicaciones deben estar en línea.</span><span class="sxs-lookup"><span data-stu-id="a8804-119">To disable publishing and distribution, all distribution and publication databases must be online.</span></span> <span data-ttu-id="a8804-120">Si existe alguna *instantánea de base de datos* para las bases de datos de distribución o de publicaciones, deben quitarse antes de deshabilitar la publicación y distribución.</span><span class="sxs-lookup"><span data-stu-id="a8804-120">If any *database snapshots* exist for distribution or publication databases, they must be dropped before disabling publishing and distribution.</span></span> <span data-ttu-id="a8804-121">Una instantánea de base de datos es una copia de solo lectura sin conexión de una base de datos y no está relacionada con una instantánea de replicación.</span><span class="sxs-lookup"><span data-stu-id="a8804-121">A database snapshot is a read-only offline copy of a database and is not related to a replication snapshot.</span></span> <span data-ttu-id="a8804-122">Para más información, vea [Instantáneas de base de datos &#40;SQL Server&#41;](../databases/database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a8804-122">For more information, see [Database Snapshots &#40;SQL Server&#41;](../databases/database-snapshots-sql-server.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a8804-123">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a8804-123">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a8804-124">Deshabilite la publicación y la distribución con el Asistente para deshabilitar la publicación y distribución.</span><span class="sxs-lookup"><span data-stu-id="a8804-124">Disable publishing and distribution by using the Disable Publishing and Distribution Wizard.</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="a8804-125">Para deshabilitar la publicación y la distribución</span><span class="sxs-lookup"><span data-stu-id="a8804-125">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="a8804-126">Conéctese al publicador o el distribuidor que quiere deshabilitar en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="a8804-126">Connect to the Publisher or Distributor you want to disable in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="a8804-127">Haga clic con el botón secundario en la carpeta **Replicación** y, a continuación, haga clic en **Deshabilitar publicación y distribución**.</span><span class="sxs-lookup"><span data-stu-id="a8804-127">Right-click the **Replication** folder, and then click **Disable Publishing and Distribution**.</span></span>  
  
3.  <span data-ttu-id="a8804-128">Siga todos los pasos del Asistente para deshabilitar la publicación y distribución.</span><span class="sxs-lookup"><span data-stu-id="a8804-128">Complete the steps in the Disable Publishing and Distribution Wizard.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a8804-129">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a8804-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="a8804-130">Puede deshabilitarse la publicación y la distribución mediante programación con los procedimientos almacenados de la replicación.</span><span class="sxs-lookup"><span data-stu-id="a8804-130">Publishing and distributing can be disabled programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="a8804-131">Para deshabilitar la publicación y la distribución</span><span class="sxs-lookup"><span data-stu-id="a8804-131">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="a8804-132">Detenga todos los trabajos relacionados con replicación.</span><span class="sxs-lookup"><span data-stu-id="a8804-132">Stop all replication-related jobs.</span></span> <span data-ttu-id="a8804-133">Para obtener una lista de nombres de tarea, vea la sección "Seguridad de agentes con el Agente SQL Server" de [Modelo de seguridad del Agente de replicación](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="a8804-133">For a list of job names, see the "Agent Security Under SQL Server Agent" section of [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
2.  <span data-ttu-id="a8804-134">En cada suscriptor de la base de datos de suscripciones, ejecute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) para quitar los objetos de replicación de dicha base de datos.</span><span class="sxs-lookup"><span data-stu-id="a8804-134">At each Subscriber on the subscription database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove replication objects from the database.</span></span> <span data-ttu-id="a8804-135">Este procedimiento almacenado no quitará los trabajos de replicación del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="a8804-135">This stored procedure will not remove replication jobs at the Distributor.</span></span>  
  
3.  <span data-ttu-id="a8804-136">En la base de datos de publicación del publicador, ejecute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) para quitar los objetos de replicación de dicha base de datos.</span><span class="sxs-lookup"><span data-stu-id="a8804-136">At the Publisher on the publication database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove replication objects from the database.</span></span>  
  
4.  <span data-ttu-id="a8804-137">Si el publicador usa un distribuidor remoto, ejecute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a8804-137">If the Publisher uses a remote Distributor, execute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql).</span></span>  
  
5.  <span data-ttu-id="a8804-138">En el distribuidor, ejecute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a8804-138">At the Distributor, execute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span></span> <span data-ttu-id="a8804-139">Este procedimiento almacenado se debería ejecutar una vez para cada publicador registrado en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="a8804-139">This stored procedure should be run once for each Publisher registered at the Distributor.</span></span>  
  
6.  <span data-ttu-id="a8804-140">En el distribuidor, ejecute [sp_dropdistributiondb](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) para eliminar la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="a8804-140">At the Distributor, execute [sp_dropdistributiondb](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) to delete the distribution database.</span></span> <span data-ttu-id="a8804-141">Este procedimiento almacenado se debería ejecutar una vez para cada base de datos de distribución en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="a8804-141">This stored procedure should be run once for each distribution database at the Distributor.</span></span> <span data-ttu-id="a8804-142">Esto también quita cualquier trabajo del Agente de lectura de cola asociado a la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="a8804-142">This also removes any Queue Reader Agent jobs associated with the distribution database.</span></span>  
  
7.  <span data-ttu-id="a8804-143">En el distribuidor, ejecute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql) para quitar la designación de distribuidor del servidor.</span><span class="sxs-lookup"><span data-stu-id="a8804-143">At the Distributor, execute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql) to remove the Distributor designation from the server.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a8804-144">Si no se quitan todos los objetos de distribución y publicación de replicación antes de ejecutar [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql) y [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql), estos procedimientos devolverán un error.</span><span class="sxs-lookup"><span data-stu-id="a8804-144">If all replication publishing and distribution objects are not dropped before you execute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql) and [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql), these procedures will return an error.</span></span> <span data-ttu-id="a8804-145">Para quitar todos los objetos relacionados con la replicación cuando se quita un publicador o un distribuidor, el parámetro \*\* \@ no_checks\*\* debe establecerse en **1**.</span><span class="sxs-lookup"><span data-stu-id="a8804-145">To drop all replication-related objects when a Publisher or Distributor is dropped, the **\@no_checks** parameter must be set to **1**.</span></span> <span data-ttu-id="a8804-146">Si un publicador o un distribuidor está sin conexión o no está accesible, el parámetro \*\* \@ ignore_distributor\*\* se puede establecer en **1** para que se puedan quitar; sin embargo, cualquier publicación y distribución de objetos restantes debe quitarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="a8804-146">If a Publisher or Distributor is offline or unreachable, the **\@ignore_distributor** parameter can be set to **1** so that they can be dropped; however, any publishing and distributing objects left behind must be removed manually.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="a8804-147">Ejemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a8804-147">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="a8804-148">Este script de ejemplo quita los objetos de replicación de la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="a8804-148">This example script removes replication objects from the subscription database.</span></span>  
  
 [!code-sql[HowTo#sp_removedbreplication](../../snippets/tsql/SQL15/replication/howto/tsql/dropdistpub.sql#sp_removedbreplication)]  
  
 <span data-ttu-id="a8804-149">Este script de ejemplo deshabilita la publicación y la distribución en un servidor que sea publicador y distribuidor, y quita la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="a8804-149">This example script disables publishing and distribution on a server that is a Publisher and Distributor and drops the distribution database.</span></span>  
  
 [!code-sql[HowTo#sp_DropDistPub](../../snippets/tsql/SQL15/replication/howto/tsql/dropdistpub.sql#sp_dropdistpub)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="a8804-150">Uso de Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="a8804-150">Using Replication Management Objects (RMO)</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="a8804-151">Para deshabilitar la publicación y la distribución</span><span class="sxs-lookup"><span data-stu-id="a8804-151">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="a8804-152">Quite todas las suscripciones a las publicaciones que usan el Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="a8804-152">Remove all subscriptions to publications that use the Distributor.</span></span> <span data-ttu-id="a8804-153">Para obtener más información, consulte [Delete a Pull Subscription](delete-a-pull-subscription.md) y [Delete a Push Subscription](delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="a8804-153">For more information, see [Delete a Pull Subscription](delete-a-pull-subscription.md) and [Delete a Push Subscription](delete-a-push-subscription.md).</span></span>  
  
2.  <span data-ttu-id="a8804-154">Quite todas las publicaciones que usan el Distribuidor y deshabilite la publicación para todas las bases de datos si el Publicador y el Distribuidor están en el mismo servidor.</span><span class="sxs-lookup"><span data-stu-id="a8804-154">Remove all publications that use the Distributor, and disable publishing for all databases if the Publisher and Distributor are on the same server.</span></span> <span data-ttu-id="a8804-155">Para más información, consulte [Delete a Publication](publish/delete-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="a8804-155">For more information, see [Delete a Publication](publish/delete-a-publication.md).</span></span>  
  
3.  <span data-ttu-id="a8804-156">Cree una conexión al distribuidor mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="a8804-156">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
4.  <span data-ttu-id="a8804-157">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.DistributionPublisher>.</span><span class="sxs-lookup"><span data-stu-id="a8804-157">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> class.</span></span> <span data-ttu-id="a8804-158">Especifique la propiedad <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> y pase el objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del paso 3.</span><span class="sxs-lookup"><span data-stu-id="a8804-158">Specify the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> property, and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 3.</span></span>  
  
5.  <span data-ttu-id="a8804-159">(Opcional) Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obtener las propiedades del objeto y compruebe que el Publicador existe.</span><span class="sxs-lookup"><span data-stu-id="a8804-159">(Optional) Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object and verify that the Publisher exists.</span></span> <span data-ttu-id="a8804-160">Si este método devuelve `false`, el nombre del Publicador establecido en el paso 4 era incorrecto o este Distribuidor no usa el Publicador.</span><span class="sxs-lookup"><span data-stu-id="a8804-160">If this method returns `false`, the Publisher name set in step 4 was incorrect or the Publisher is not used by this Distributor.</span></span>  
  
6.  <span data-ttu-id="a8804-161">Llame al método <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="a8804-161">Call the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Remove%2A> method.</span></span> <span data-ttu-id="a8804-162">Pase un valor de `true` para *Force* si el publicador y el distribuidor están en servidores diferentes, y cuando el publicador se debe desinstalar en el distribuidor sin comprobar primero que las publicaciones ya no existen en el publicador.</span><span class="sxs-lookup"><span data-stu-id="a8804-162">Pass a value of `true` for *force* if the Publisher and Distributor are on different servers, and when the Publisher should be uninstalled at the Distributor without first verifying that publications no longer exist at the Publisher.</span></span>  
  
7.  <span data-ttu-id="a8804-163">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="a8804-163">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="a8804-164">Pase el objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del paso 3.</span><span class="sxs-lookup"><span data-stu-id="a8804-164">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 3.</span></span>  
  
8.  <span data-ttu-id="a8804-165">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationServer.UninstallDistributor%2A> .</span><span class="sxs-lookup"><span data-stu-id="a8804-165">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.UninstallDistributor%2A> method.</span></span> <span data-ttu-id="a8804-166">Pase un valor de `true` for *Force* para quitar todos los objetos de replicación en el distribuidor sin comprobar primero que todas las bases de datos de publicación locales se han deshabilitado y que se han desinstalado las bases de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="a8804-166">Pass a value of `true` for *force* to remove all replication objects at the Distributor without first verifying that all local publication databases have been disabled, and distribution databases have been uninstalled.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="a8804-167">Ejemplos (RMO)</span><span class="sxs-lookup"><span data-stu-id="a8804-167">Examples (RMO)</span></span>  
 <span data-ttu-id="a8804-168">Este ejemplo quita el registro del Publicador en el Distribuidor, coloca la base de datos de distribución y desinstala el Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="a8804-168">This example removes the Publisher registration at the Distributor, drops the distribution database, and uninstalls the Distributor.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropDistPub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropdistpub)]  
  
 [!code-vb[HowTo#rmo_vb_DropDistPub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropdistpub)]  
  
 <span data-ttu-id="a8804-169">Este ejemplo desinstala el Distribuidor sin deshabilitar primero las bases de datos de publicación locales o quitar la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="a8804-169">This example uninstalls the Distributor without first disabling local publication databases or dropping the distribution database.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropDistPubForce](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropdistpubforce)]  
  
 [!code-vb[HowTo#rmo_vb_DropDistPubForce](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropdistpubforce)]  
  
## <a name="see-also"></a><span data-ttu-id="a8804-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8804-170">See Also</span></span>  
 <span data-ttu-id="a8804-171">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="a8804-171">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 [<span data-ttu-id="a8804-172">Conceptos de procedimientos almacenados del sistema de replicación</span><span class="sxs-lookup"><span data-stu-id="a8804-172">Replication System Stored Procedures Concepts</span></span>](concepts/replication-system-stored-procedures-concepts.md)  
  
  
