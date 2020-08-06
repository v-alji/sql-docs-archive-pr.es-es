---
title: Ver y modificar las propiedades del distribuidor y del publicador | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- viewing replication properties
- Distributors [SQL Server replication], modifying
- modifying replication properties, Distributors
- Distributors [SQL Server replication], properties
ms.assetid: 5dae1d59-c377-4c6e-adc9-b68c5b328f79
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 571f6f3a0d44f0fc87c67885249fca441776946d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670914"
---
# <a name="view-and-modify-distributor-and-publisher-properties"></a><span data-ttu-id="af188-102">Ver y modificar las propiedades del distribuidor y del publicador</span><span class="sxs-lookup"><span data-stu-id="af188-102">View and Modify Distributor and Publisher Properties</span></span>
  <span data-ttu-id="af188-103">En este tema se describe cómo ver y modificar las propiedades del distribuidor y del publicador en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="af188-103">This topic describes how to view and modify Distributor and Publisher properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="af188-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="af188-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="af188-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="af188-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="af188-106">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="af188-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="af188-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="af188-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="af188-108">**Para ver y modificar las propiedades del publicador y del distribuidor con:**</span><span class="sxs-lookup"><span data-stu-id="af188-108">**To view and modify Distributor and Publisher properties, using:**</span></span>  
  
     [<span data-ttu-id="af188-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="af188-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="af188-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="af188-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="af188-111">Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="af188-111">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="af188-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="af188-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="af188-113">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="af188-113">Recommendations</span></span>  
  
-   <span data-ttu-id="af188-114">Para los publicadores que ejecutan versiones anteriores a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], un usuario del rol fijo de servidor **sysadmin** puede registrar suscriptores en la página **Suscriptores**.</span><span class="sxs-lookup"><span data-stu-id="af188-114">For Publishers running versions prior to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a user in the **sysadmin** fixed server role can register Subscribers on the **Subscribers** page.</span></span> <span data-ttu-id="af188-115">A partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], ya no es necesario registrar explícitamente los suscriptores para la replicación.</span><span class="sxs-lookup"><span data-stu-id="af188-115">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], it is no longer necessary to explicitly register Subscribers for replication.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="af188-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="af188-116">Security</span></span>  
 <span data-ttu-id="af188-117">Cuando sea posible, pida a los usuarios que proporcionen credenciales de seguridad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="af188-117">When possible, prompt users to enter security credentials at runtime.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="af188-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="af188-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-and-modify-distributor-properties"></a><span data-ttu-id="af188-119">Para ver y modificar las propiedades del distribuidor</span><span class="sxs-lookup"><span data-stu-id="af188-119">To view and modify Distributor properties</span></span>  
  
1.  <span data-ttu-id="af188-120">Conéctese al distribuidor en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]y expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="af188-120">Connect to the Distributor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="af188-121">Haga clic con el botón secundario en la carpeta **Replicación** y, a continuación, haga clic en **Propiedades del distribuidor**.</span><span class="sxs-lookup"><span data-stu-id="af188-121">Right-click the **Replication** folder, and then click **Distributor Properties**.</span></span>  
  
3.  <span data-ttu-id="af188-122">Vea y modifique las propiedades en el cuadro de diálogo **Propiedades del distribuidor - \<Distributor>** .</span><span class="sxs-lookup"><span data-stu-id="af188-122">View and modify properties in the **Distributor Properties - \<Distributor>** dialog box.</span></span>  
  
    -   <span data-ttu-id="af188-123">Para ver y modificar las propiedades de una base de datos de distribución, haga clic en el botón de propiedades ( **...** ) de la base de datos en la página **General** del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="af188-123">To view and modify properties for a distribution database, click the properties button (**...**) for the database on the **General** page of thedialog box.</span></span>  
  
    -   <span data-ttu-id="af188-124">Para ver y modificar las propiedades del publicador asociado al distribuidor, haga clic en el botón de propiedades ( **...** ) del publicador en el cuadro de diálogo **publicador** .</span><span class="sxs-lookup"><span data-stu-id="af188-124">To view and modify Publisher properties associated with the Distributor, click the properties button (**...**) for the Publisher on the **Publishers** page of the dialog box.</span></span>  
  
    -   <span data-ttu-id="af188-125">Para obtener acceso a los perfiles de los agentes de replicación, haga clic en el botón **Valores predeterminados de perfil** de la página **General** del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="af188-125">To access profiles for replication agents, click the **Profile Defaults** button on the **General** page of the dialog box.</span></span> <span data-ttu-id="af188-126">Para obtener más información, consulte [Replication Agent Profiles](agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="af188-126">For more information, see [Replication Agent Profiles](agents/replication-agent-profiles.md).</span></span>  
  
    -   <span data-ttu-id="af188-127">Para cambiar la contraseña de la cuenta utilizada cuando los procedimientos almacenados administrativos se ejecutan en el publicador y actualizar la información del distribuidor, escriba una contraseña nueva en los cuadros **Contraseña** y **Confirmar contraseña** de la página **Publicadores** del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="af188-127">To change the password for the account used when administrative stored procedures execute at the Publisher and update information at the Distributor, enter a new password in the **Password** and **Confirm password** boxes on the **Publishers** page of the dialog box.</span></span> <span data-ttu-id="af188-128">Para más información, vea [Proteger el distribuidor](security/secure-the-distributor.md).</span><span class="sxs-lookup"><span data-stu-id="af188-128">For more information, see [Secure the Distributor](security/secure-the-distributor.md).</span></span>  
  
4.  <span data-ttu-id="af188-129">Modifique las propiedades si es necesario y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="af188-129">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-publisher-properties"></a><span data-ttu-id="af188-130">Para ver y modificar las propiedades del Publicador</span><span class="sxs-lookup"><span data-stu-id="af188-130">To view and modify Publisher properties</span></span>  
  
1.  <span data-ttu-id="af188-131">Conéctese al publicador en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]y luego expanda el nodo del servidor.</span><span class="sxs-lookup"><span data-stu-id="af188-131">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="af188-132">Haga clic con el botón secundario en la carpeta **Replicación** y, a continuación, haga clic en **Propiedades del publicador**.</span><span class="sxs-lookup"><span data-stu-id="af188-132">Right-click the **Replication** folder, and then click **Publisher Properties**.</span></span>  
  
3.  <span data-ttu-id="af188-133">Vea y modifique las propiedades en el cuadro de diálogo \*\*propiedades del publicador: \< Publisher > \*\* .</span><span class="sxs-lookup"><span data-stu-id="af188-133">View and modify properties in the **Publisher Properties - \< Publisher >** dialog box.</span></span>  
  
    -   <span data-ttu-id="af188-134">Un usuario del rol fijo de servidor **sysadmin** puede habilitar bases de datos de replicación en la página **Bases de datos de publicaciones** .</span><span class="sxs-lookup"><span data-stu-id="af188-134">A user in the **sysadmin** fixed server role can enable databases for replication on the **Publication Databases** page.</span></span> <span data-ttu-id="af188-135">Al habilitar una base de datos no se publica dicha base de datos, sino que permite que cualquier usuario del rol fijo de base de datos **db_owner** para esa base de datos cree una o varias publicaciones en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="af188-135">Enabling a database does not publish that database; rather, it allows any user in the **db_owner** fixed database role for that database to create one or more publications in the database.</span></span>  
  
4.  <span data-ttu-id="af188-136">Modifique las propiedades si es necesario y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="af188-136">Modify any properties if necessary, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="af188-137">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="af188-137">Using Transact-SQL</span></span>  
 <span data-ttu-id="af188-138">Las propiedades del publicador y del distributor se pueden ver mediante programación usando procedimientos almacenados de replicación.</span><span class="sxs-lookup"><span data-stu-id="af188-138">Publisher and Distributor properties can be viewed programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-view-distributor-and-distribution-database-properties"></a><span data-ttu-id="af188-139">Para ver las propiedades de la base de datos de distribución</span><span class="sxs-lookup"><span data-stu-id="af188-139">To view Distributor and distribution database properties</span></span>  
  
1.  <span data-ttu-id="af188-140">Ejecute [sp_helpdistributor](/sql/relational-databases/system-stored-procedures/sp-helpdistributor-transact-sql) para devolver información sobre el Distribuidor, la base de datos de distribución y el directorio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af188-140">Execute [sp_helpdistributor](/sql/relational-databases/system-stored-procedures/sp-helpdistributor-transact-sql) to return information about the Distributor, distribution database, and working directory.</span></span>  
  
2.  <span data-ttu-id="af188-141">Ejecute [sp_helpdistributiondb](/sql/relational-databases/system-stored-procedures/sp-helpdistributiondb-transact-sql) para devolver propiedades de una base de datos de distribución especificada.</span><span class="sxs-lookup"><span data-stu-id="af188-141">Execute [sp_helpdistributiondb](/sql/relational-databases/system-stored-procedures/sp-helpdistributiondb-transact-sql) to return properties of a specified distribution database.</span></span>  
  
#### <a name="to-change-distributor-and-distribution-database-properties"></a><span data-ttu-id="af188-142">Para cambiar las propiedades de la base de datos de distribución y el distribuidor</span><span class="sxs-lookup"><span data-stu-id="af188-142">To change Distributor and distribution database properties</span></span>  
  
1.  <span data-ttu-id="af188-143">En el distribuidor, ejecute [sp_changedistributor_property](/sql/relational-databases/system-stored-procedures/sp-changedistributor-property-transact-sql) para modificar las propiedades del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="af188-143">At the Distributor, execute [sp_changedistributor_property](/sql/relational-databases/system-stored-procedures/sp-changedistributor-property-transact-sql) to modify Distributor properties.</span></span>  
  
2.  <span data-ttu-id="af188-144">En el distribuidor, ejecute [sp_changedistributor_property](/sql/relational-databases/system-stored-procedures/sp-changedistributiondb-transact-sql) para modificar las propiedades del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="af188-144">At the Distributor, execute [sp_changedistributiondb](/sql/relational-databases/system-stored-procedures/sp-changedistributiondb-transact-sql) to modify distribution database properties.</span></span>  
  
3.  <span data-ttu-id="af188-145">En el distribuidor, ejecute [sp_changedistributor_password](/sql/relational-databases/system-stored-procedures/sp-changedistributor-password-transact-sql) para cambiar la contraseña del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="af188-145">At the Distributor, execute [sp_changedistributor_password](/sql/relational-databases/system-stored-procedures/sp-changedistributor-password-transact-sql) to change the Distributor password.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="af188-146">Cuando sea posible, pida a los usuarios que proporcionen credenciales de seguridad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="af188-146">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="af188-147">Si debe almacenar credenciales en un archivo de script, proteja el archivo para evitar el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="af188-147">If you must store credentials in a script file, secure the file to prevent unauthorized access.</span></span>  
  
4.  <span data-ttu-id="af188-148">En el distribuidor, ejecute [sp_changedistpublisher](/sql/relational-databases/system-stored-procedures/sp-changedistpublisher-transact-sql) para cambiar las propiedades de un Publicador usando el Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="af188-148">At the Distributor, execute [sp_changedistpublisher](/sql/relational-databases/system-stored-procedures/sp-changedistpublisher-transact-sql) to change the properties of a Publisher using the Distributor.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="af188-149">Ejemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="af188-149">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="af188-150">El siguiente script de [!INCLUDE[tsql](../../includes/tsql-md.md)] de ejemplo devuelve información acerca del Distribuidor y la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="af188-150">The following example [!INCLUDE[tsql](../../includes/tsql-md.md)] script returns information about the Distributor and distribution database.</span></span>  
  
 [!code-sql[HowTo#sp_helpdistributor](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_helpdistributor)]  
  
 [!code-sql[HowTo#sp_helpdistributiondb](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_helpdistributiondb)]  
  
 <span data-ttu-id="af188-151">Este ejemplo cambia los períodos de retención para el Distribuidor, la contraseña usada al conectar al Distribuidor y el intervalo en el que el Distribuidor comprueba el estado de distintos agentes de replicación (también conocido como intervalo de latidos).</span><span class="sxs-lookup"><span data-stu-id="af188-151">This example changes retention periods for the Distributor, the password used when connecting to the Distributor, and the interval at which the Distributor checks the status of various replication agents (also known as the heartbeat interval).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="af188-152">Cuando sea posible, pida a los usuarios que proporcionen credenciales de seguridad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="af188-152">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="af188-153">Si debe almacenar credenciales en un archivo de script, proteja el archivo para evitar el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="af188-153">If you must store credentials in a script file, secure the file to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_changedistributor_property](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributor_property)]  
  
 [!code-sql[HowTo#sp_changedistributiondb](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributiondb)]  
  
 [!code-sql[HowTo#sp_changedistributor_password](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributor_password)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="af188-154">Uso de Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="af188-154">Using Replication Management Objects (RMO)</span></span>  
  
#### <a name="to-view-and-modify-distributor-properties"></a><span data-ttu-id="af188-155">Para ver y modificar las propiedades del distribuidor</span><span class="sxs-lookup"><span data-stu-id="af188-155">To view and modify Distributor properties</span></span>  
  
1.  <span data-ttu-id="af188-156">Cree una conexión al distribuidor mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="af188-156">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="af188-157">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="af188-157">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="af188-158">Pase el objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del paso 1.</span><span class="sxs-lookup"><span data-stu-id="af188-158">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="af188-159">(Opcional) Compruebe la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationServer.IsDistributor%2A> para comprobar que el servidor conectado actualmente es un distribuidor.</span><span class="sxs-lookup"><span data-stu-id="af188-159">(Optional) Check the <xref:Microsoft.SqlServer.Replication.ReplicationServer.IsDistributor%2A> property to verify that the currently connected server is a Distributor.</span></span>  
  
4.  <span data-ttu-id="af188-160">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> para recibir las propiedades del servidor.</span><span class="sxs-lookup"><span data-stu-id="af188-160">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties from the server.</span></span>  
  
5.  <span data-ttu-id="af188-161">(Opcional) Para cambiar las propiedades, establezca un nuevo valor para una o más de las propiedades del distribuidor que se pueden establecer en el objeto <xref:Microsoft.SqlServer.Replication.ReplicationServer> .</span><span class="sxs-lookup"><span data-stu-id="af188-161">(Optional) To change properties, set a new value for one or more of the Distributor properties that can be set on the <xref:Microsoft.SqlServer.Replication.ReplicationServer> object.</span></span>  
  
6.  <span data-ttu-id="af188-162">(Opcional) Si la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> del objeto <xref:Microsoft.SqlServer.Replication.ReplicationServer> está establecida en `true`, llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> para confirmar los cambios en el servidor.</span><span class="sxs-lookup"><span data-stu-id="af188-162">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.ReplicationServer> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-view-and-modify-distribution-database-properties"></a><span data-ttu-id="af188-163">Para ver y modificar las propiedades de la base de datos de distribución</span><span class="sxs-lookup"><span data-stu-id="af188-163">To view and modify distribution database properties</span></span>  
  
1.  <span data-ttu-id="af188-164">Cree una conexión al distribuidor mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="af188-164">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="af188-165">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.DistributionDatabase>.</span><span class="sxs-lookup"><span data-stu-id="af188-165">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> class.</span></span> <span data-ttu-id="af188-166">Especifique la propiedad de nombre y pase el objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del paso 1.</span><span class="sxs-lookup"><span data-stu-id="af188-166">Specify the name property and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="af188-167">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para recibir las propiedades del servidor.</span><span class="sxs-lookup"><span data-stu-id="af188-167">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties from the server.</span></span> <span data-ttu-id="af188-168">Si este método devuelve `false`, significa que la base de datos con el nombre especificado no existe en el servidor.</span><span class="sxs-lookup"><span data-stu-id="af188-168">If this method returns `false`, the database with the specified name does not exist on the server.</span></span>  
  
4.  <span data-ttu-id="af188-169">(Opcional) Para cambiar las propiedades, establezca un nuevo valor para una de las propiedades <xref:Microsoft.SqlServer.Replication.DistributionDatabase> que se pueden establecer.</span><span class="sxs-lookup"><span data-stu-id="af188-169">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> properties that can be set.</span></span>  
  
5.  <span data-ttu-id="af188-170">(Opcional) Si la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> del objeto <xref:Microsoft.SqlServer.Replication.DistributionDatabase> está establecida en `true`, llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> para confirmar los cambios en el servidor.</span><span class="sxs-lookup"><span data-stu-id="af188-170">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-view-and-modify-publisher-properties"></a><span data-ttu-id="af188-171">Para ver y modificar las propiedades del Publicador</span><span class="sxs-lookup"><span data-stu-id="af188-171">To view and modify Publisher properties</span></span>  
  
1.  <span data-ttu-id="af188-172">Cree una conexión al publicador mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="af188-172">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="af188-173">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.DistributionPublisher>.</span><span class="sxs-lookup"><span data-stu-id="af188-173">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> class.</span></span> <span data-ttu-id="af188-174">Especifique la propiedad <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> y pase el objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> del paso 1.</span><span class="sxs-lookup"><span data-stu-id="af188-174">Specify the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> property and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="af188-175">(Opcional) Para cambiar las propiedades, establezca un nuevo valor para una de las propiedades <xref:Microsoft.SqlServer.Replication.DistributionPublisher> que se pueden establecer.</span><span class="sxs-lookup"><span data-stu-id="af188-175">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> properties that can be set.</span></span>  
  
4.  <span data-ttu-id="af188-176">(Opcional) Si la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> del objeto <xref:Microsoft.SqlServer.Replication.DistributionPublisher> está establecida en `true`, llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> para confirmar los cambios en el servidor.</span><span class="sxs-lookup"><span data-stu-id="af188-176">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-change-the-password-for-the-administrative-connection-from-the-publisher-to-the-distributor"></a><span data-ttu-id="af188-177">Para cambiar la contraseña de la conexión administrativa del publicador al distribuidor</span><span class="sxs-lookup"><span data-stu-id="af188-177">To change the password for the administrative connection from the Publisher to the Distributor</span></span>  
  
1.  <span data-ttu-id="af188-178">Cree una conexión al distribuidor mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="af188-178">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="af188-179">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="af188-179">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span>  
  
3.  <span data-ttu-id="af188-180">Establezca la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> en la conexión creada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="af188-180">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="af188-181">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> para obtener las propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="af188-181">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties of the object.</span></span>  
  
5.  <span data-ttu-id="af188-182">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> .</span><span class="sxs-lookup"><span data-stu-id="af188-182">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> method.</span></span> <span data-ttu-id="af188-183">Pase el nuevo valor de contraseña para el parámetro *password* .</span><span class="sxs-lookup"><span data-stu-id="af188-183">Pass the new password value for the *password* parameter.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="af188-184">Cuando sea posible, pida a los usuarios que proporcionen credenciales de seguridad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="af188-184">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="af188-185">Si debe almacenar credenciales, use los [servicios de cifrado](https://go.microsoft.com/fwlink/?LinkId=34733) (en inglés) proporcionados por [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="af188-185">If you must store credentials, use the [cryptographic services](https://go.microsoft.com/fwlink/?LinkId=34733) provided by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows .NET Framework.</span></span>  
  
6.  <span data-ttu-id="af188-186">(Opcional) Realice los pasos siguientes para cambiar la contraseña en cada publicador remoto que utilice este distribuidor:</span><span class="sxs-lookup"><span data-stu-id="af188-186">(Optional) Perform the following steps to change the password at each remote Publisher that uses this Distributor:</span></span>  
  
    1.  <span data-ttu-id="af188-187">Cree una conexión al publicador mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="af188-187">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
    2.  <span data-ttu-id="af188-188">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="af188-188">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span>  
  
    3.  <span data-ttu-id="af188-189">Establezca la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> en la conexión creada en el paso 6a.</span><span class="sxs-lookup"><span data-stu-id="af188-189">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 6a.</span></span>  
  
    4.  <span data-ttu-id="af188-190">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> para obtener las propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="af188-190">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties of the object.</span></span>  
  
    5.  <span data-ttu-id="af188-191">Llame al método <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> .</span><span class="sxs-lookup"><span data-stu-id="af188-191">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> method.</span></span> <span data-ttu-id="af188-192">Pase el nuevo valor de contraseña del paso 5 para el parámetro *password* .</span><span class="sxs-lookup"><span data-stu-id="af188-192">Pass the new password value from Step 5 for the *password* parameter.</span></span>  
  
###  <a name="example-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="af188-193">Ejemplo (RMO)</span><span class="sxs-lookup"><span data-stu-id="af188-193">Example (RMO)</span></span>  
 <span data-ttu-id="af188-194">Este ejemplo muestra cómo cambiar las propiedades de Distribución y de la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="af188-194">This example shows how to change Distribution and distribution database properties.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="af188-195">Para no almacenar las credenciales en el código, la nueva contraseña del distribuidor se proporciona en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="af188-195">To avoid storing credentials in the code, the new Distributor password is supplied at runtime.</span></span>  
  
 [!code-csharp[HowTo#rmo_ChangeDistPub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_changedistpub)]  
  
 [!code-vb[HowTo#rmo_vb_ChangeDistPub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_changedistpub)]  
  
## <a name="see-also"></a><span data-ttu-id="af188-196">Consulte también</span><span class="sxs-lookup"><span data-stu-id="af188-196">See Also</span></span>  
 <span data-ttu-id="af188-197">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="af188-197">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="af188-198">[Disable Publishing and Distribution](disable-publishing-and-distribution.md)  (Deshabilitar la publicación y la distribución)</span><span class="sxs-lookup"><span data-stu-id="af188-198">[Disable Publishing and Distribution](disable-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="af188-199">[Configurar distribución](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="af188-199">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="af188-200">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="af188-200">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="af188-201">[Distributor and Publisher Information Script](administration/distributor-and-publisher-information-script.md)  (Script de información del distribuidor y del publicador)</span><span class="sxs-lookup"><span data-stu-id="af188-201">[Distributor and Publisher Information Script](administration/distributor-and-publisher-information-script.md) </span></span>  
 <span data-ttu-id="af188-202">[Replication System Stored Procedures Concepts](concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="af188-202">[Replication System Stored Procedures Concepts](concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="af188-203">Ver información y realizar tareas mediante el monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="af188-203">View Information and Perform Tasks using Replication Monitor</span></span>](monitor/view-information-and-perform-tasks-replication-monitor.md)  
  
  
