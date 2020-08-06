---
title: Configurar la replicación para grupos de disponibilidad AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 4e001426-5ae0-4876-85ef-088d6e3fb61c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 916458d2d6b8fbba81940257ee85ffe014d1f12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744873"
---
# <a name="configure-replication-for-always-on-availability-groups-sql-server"></a><span data-ttu-id="31816-102">Configurar la replicación para grupos de disponibilidad AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31816-102">Configure Replication for Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="31816-103">La configuración de la replicación y los grupos de disponibilidad AlwaysOn de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requiere siete pasos.</span><span class="sxs-lookup"><span data-stu-id="31816-103">Configuring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] replication and AlwaysOn availability groups involves seven steps.</span></span> <span data-ttu-id="31816-104">Cada paso se describe con más detalle en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="31816-104">Each step is described in more detail in the following sections.</span></span>  

##  <a name="1-configure-the-database-publications-and-subscriptions"></a><a name="step1"></a> <span data-ttu-id="31816-105">1. Configurar las publicaciones y suscripciones de la base de datos</span><span class="sxs-lookup"><span data-stu-id="31816-105">1. Configure the Database Publications and Subscriptions</span></span>  

### <a name="configure-the-distributor"></a><span data-ttu-id="31816-106">Configurar el distribuidor</span><span class="sxs-lookup"><span data-stu-id="31816-106">Configure the distributor</span></span>
  
 <span data-ttu-id="31816-107">El distribuidor no debe ser un host para ninguna de las réplicas actuales (o previstas) del grupo de disponibilidad del que la base de datos de publicación es (o será) un miembro.</span><span class="sxs-lookup"><span data-stu-id="31816-107">The distributor should not be a host for any of the current (or intended) replicas of the availability group that the publishing database is (or will become) a member of.</span></span>  
  
1.  <span data-ttu-id="31816-108">Configure la distribución en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="31816-108">Configure distribution at the distributor.</span></span> <span data-ttu-id="31816-109">Si se utilizan procedimientos almacenados para la configuración, ejecute `sp_adddistributor`.</span><span class="sxs-lookup"><span data-stu-id="31816-109">If stored procedures are being used for configuration, run `sp_adddistributor`.</span></span> <span data-ttu-id="31816-110">Use el *@password* parámetro para identificar la contraseña que se utilizará cuando un publicador remoto se conecte al distribuidor.</span><span class="sxs-lookup"><span data-stu-id="31816-110">Use the *@password* parameter to identify the password that will be used when a remote publisher connects to the distributor.</span></span> <span data-ttu-id="31816-111">También se necesitará la contraseña de cada publicador remoto cuando el distribuidor remoto está configurado.</span><span class="sxs-lookup"><span data-stu-id="31816-111">The password will also be needed at each remote publisher when the remote distributor is set up.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_adddistributor  
        @distributor = 'MyDistributor',  
        @password = '**Strong password for distributor**';  
    ```  
  
2.  <span data-ttu-id="31816-112">Cree la base de datos de distribución en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="31816-112">Create the distribution database at the distributor.</span></span> <span data-ttu-id="31816-113">Si se utilizan procedimientos almacenados para la configuración, ejecute `sp_adddistributiondb`.</span><span class="sxs-lookup"><span data-stu-id="31816-113">If stored procedures are being used for configuration, run `sp_adddistributiondb`.</span></span>  
  
    ```  
    USE master;  
    GO  
    EXEC sys.sp_adddistributiondb  
        @database = 'distribution',  
        @security_mode = 1;  
    ```  
  
3.  <span data-ttu-id="31816-114">Configure el publicador remoto.</span><span class="sxs-lookup"><span data-stu-id="31816-114">Configure the remote publisher.</span></span> <span data-ttu-id="31816-115">Si se utilizan procedimientos almacenados para configurar el distribuidor, ejecute `sp_adddistpublisher`.</span><span class="sxs-lookup"><span data-stu-id="31816-115">If stored procedures are being used to configure the distributor, run `sp_adddistpublisher`.</span></span> <span data-ttu-id="31816-116">El *@security_mode* parámetro se utiliza para determinar cómo el procedimiento almacenado de validación del publicador que se ejecuta desde los agentes de replicación se conecta a la principal actual.</span><span class="sxs-lookup"><span data-stu-id="31816-116">The *@security_mode* parameter is used to determine how the publisher validation stored procedure that is run from the replication agents, connects to the current primary.</span></span> <span data-ttu-id="31816-117">Si se establece en 1, la autenticación de Windows se usa para conectarse a la réplica principal actual.</span><span class="sxs-lookup"><span data-stu-id="31816-117">If set to 1 Windows authentication is used to connect to the current primary.</span></span> <span data-ttu-id="31816-118">Si se establece en 0, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] la autenticación se utiliza con los *@login* valores y especificados *@password* .</span><span class="sxs-lookup"><span data-stu-id="31816-118">If set to 0, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] authentication is used with the specified *@login* and *@password* values.</span></span> <span data-ttu-id="31816-119">El inicio de sesión y la contraseña especificados deben ser válidos en cada réplica secundaria para que el procedimiento almacenado de validación se conecte correctamente a esa réplica.</span><span class="sxs-lookup"><span data-stu-id="31816-119">The login and password specified must be valid at each secondary replica for the validation stored procedure to successfully connect to that replica.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="31816-120">Si algunos agentes de replicación modificados se ejecutan en un equipo distinto del distribuidor, el uso de la autenticación de Windows para la conexión a la principal requerirá que la autenticación Kerberos se configure para la comunicación entre equipos host de réplica.</span><span class="sxs-lookup"><span data-stu-id="31816-120">If any modified replication agents run on a computer other than the distributor, use of Windows authentication for the connection to the primary will require Kerberos authentication to be configured for the communication between the replica host computers.</span></span> <span data-ttu-id="31816-121">El uso de un inicio de sesión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para la conexión a la principal actual no necesita la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="31816-121">Use of a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login for the connection to the current primary will not require Kerberos authentication.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_adddistpublisher  
        @publisher = 'AGPrimaryReplicaHost',  
        @distribution_db = 'distribution',  
        @working_directory = '\\MyReplShare\WorkingDir',  
        @login = 'MyPubLogin',  
        @password = '**Strong password for publisher**';  
    ```  
  
 <span data-ttu-id="31816-122">Para obtener más información, vea [sp_adddistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="31816-122">For more information, see [sp_adddistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistpublisher-transact-sql).</span></span>  
  
### <a name="configure-the-publisher-at-the-original-publisher"></a><span data-ttu-id="31816-123">Configurar el publicador en el publicador original</span><span class="sxs-lookup"><span data-stu-id="31816-123">Configure the publisher at the original publisher</span></span>
  
1.  <span data-ttu-id="31816-124">Configure el distribuidor remoto.</span><span class="sxs-lookup"><span data-stu-id="31816-124">Configure remote distribution.</span></span> <span data-ttu-id="31816-125">Si se emplean procedimientos almacenados para configurar el publicador, ejecute `sp_adddistributor`.</span><span class="sxs-lookup"><span data-stu-id="31816-125">If stored procedures are being used to configure the publisher, run `sp_adddistributor`.</span></span> <span data-ttu-id="31816-126">Especifique el mismo valor para *@password* que el que se utilizó cuando `sp_adddistrbutor` se ejecutó en el distribuidor para configurar la distribución.</span><span class="sxs-lookup"><span data-stu-id="31816-126">Specify the same value for *@password* as that used when `sp_adddistrbutor` was run at the distributor to set up distribution.</span></span>  
  
    ```sql
    exec sys.sp_adddistributor  
        @distributor = 'MyDistributor',  
        @password = 'MyDistPass'  
    ```  
  
2.  <span data-ttu-id="31816-127">Habilite la base de datos para replicación.</span><span class="sxs-lookup"><span data-stu-id="31816-127">Enable the database for replication.</span></span> <span data-ttu-id="31816-128">Si se emplean procedimientos almacenados para configurar el publicador, ejecute `sp_replicationdboption`.</span><span class="sxs-lookup"><span data-stu-id="31816-128">If stored procedures are being used to configure the publisher, run `sp_replicationdboption`.</span></span> <span data-ttu-id="31816-129">Si la replicación transaccional y de mezcla se configuran para la base de datos, cada una debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="31816-129">If both transactional and merge replication are to be configured for the database, each must be enabled.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'publish',  
        @value = 'true';  
  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'merge publish',  
        @value = 'true';  
    ```  
  
3.  <span data-ttu-id="31816-130">Cree la publicación de replicación, los artículos y las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="31816-130">Create the replication publication, articles, and subscriptions.</span></span> <span data-ttu-id="31816-131">Para obtener más información acerca de cómo configurar la replicación, vea los objetos Publicar datos y Base de datos.</span><span class="sxs-lookup"><span data-stu-id="31816-131">For more information about how to configure replication, see Publishing Data and Database objects.</span></span>  
  
##  <a name="2-configure-the-alwayson-availability-group"></a><a name="step2"></a><span data-ttu-id="31816-132">2. configurar el grupo de disponibilidad AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="31816-132">2. Configure the AlwaysOn Availability Group</span></span>  
 <span data-ttu-id="31816-133">En la principal deseada, cree el grupo de disponibilidad con la base de datos publicada (o que va a ser publicada) como una base de datos de miembros.</span><span class="sxs-lookup"><span data-stu-id="31816-133">At the intended primary, create the availability group with the published (or to be published) database as a member database.</span></span> <span data-ttu-id="31816-134">Si usa el Asistente para grupo de disponibilidad, puede permitir que el asistente sincronice inicialmente las bases de datos de réplica secundaria o puede realizar la inicialización manualmente mediante copias de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="31816-134">If using the Availability Group Wizard, you can either allow the wizard to initially synchronize the secondary replica databases or you can perform the initialization manually by using backup and restore.</span></span>  
  
 <span data-ttu-id="31816-135">Cree un agente de escucha DNS para el grupo de disponibilidad que utilizarán los agentes de replicación para conectarse a la principal actual.</span><span class="sxs-lookup"><span data-stu-id="31816-135">Create a DNS listener for the availability group that will be used by the replication agents to connect to the current primary.</span></span> <span data-ttu-id="31816-136">El nombre del agente de escucha especificado se utilizará como el destino de la redirección para el par publicador original y base de datos publicada.</span><span class="sxs-lookup"><span data-stu-id="31816-136">The listener name that is specified will be used as the target of redirection for the original publisher/published database pair.</span></span> <span data-ttu-id="31816-137">Por ejemplo, si utiliza DDL para configurar el grupo de disponibilidad, el siguiente ejemplo de código se puede usar para especificar un agente de escucha para un grupo de disponibilidad denominado `MyAG`:</span><span class="sxs-lookup"><span data-stu-id="31816-137">For example, if you are using DDL to configure the availability group, the following code example can be used to specify an availability group listener for an existing availability group named `MyAG`:</span></span>  
  
```sql
ALTER AVAILABILITY GROUP 'MyAG'   
    ADD LISTENER 'MyAGListenerName' (WITH IP (('10.120.19.155', '255.255.254.0')));  
```  
  
 <span data-ttu-id="31816-138">Para obtener más información, vea [Creación y configuración de grupos de disponibilidad &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="31816-138">For more information, see [Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md).</span></span>  
  
##  <a name="3-insure-that-all-of-the-secondary-replica-hosts-are-configured-for-replication"></a><a name="step3"></a><span data-ttu-id="31816-139">3. asegurarse de que todos los hosts de la réplica secundaria están configurados para la replicación</span><span class="sxs-lookup"><span data-stu-id="31816-139">3. Insure that all of the Secondary Replica Hosts are Configured for Replication</span></span>  
 <span data-ttu-id="31816-140">Compruebe que se ha configurado [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en cada host de réplica secundaria para admitir la replicación.</span><span class="sxs-lookup"><span data-stu-id="31816-140">At each secondary replica host, verify that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has been configured to support replication.</span></span> <span data-ttu-id="31816-141">La siguiente consulta se puede ejecutar en cada host de réplica secundaria para determinar si está instalada la replicación:</span><span class="sxs-lookup"><span data-stu-id="31816-141">The following query can be run at each secondary replica host to determine whether replication is installed:</span></span>  
  
```sql
USE master;  
GO  
DECLARE @installed int;  
EXEC @installed = sys.sp_MS_replication_installed;  
SELECT @installed;  
```  
  
 <span data-ttu-id="31816-142">Si *@installed* es 0, se debe agregar la replicación a la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="31816-142">If *@installed* is 0, replication must be added to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation.</span></span>  
  
##  <a name="4-configure-the-secondary-replica-hosts-as-replication-publishers"></a><a name="step4"></a> <span data-ttu-id="31816-143">4. Configurar los hosts de la réplica secundaria como publicadores de replicación</span><span class="sxs-lookup"><span data-stu-id="31816-143">4. Configure the Secondary Replica Hosts as Replication Publishers</span></span>  
 <span data-ttu-id="31816-144">Una réplica secundaria no puede actuar como un publicador o republicador de la replicación, pero la replicación debe configurarse de modo que la secundaria pueda asumir el control después de una conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="31816-144">A secondary replica cannot act as a replication publisher or republisher but replication must be configured so that the secondary can take over after a failover.</span></span> <span data-ttu-id="31816-145">En el distribuidor, configure la distribución para cada host de réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="31816-145">At the distributor, configure distribution for each secondary replica host.</span></span> <span data-ttu-id="31816-146">Especifique la misma base de datos de distribución y directorio de trabajo que se especificó cuando se agregó el publicador original en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="31816-146">Specify the same distribution database and working directory as was specified when the original publisher was added to the distributor.</span></span> <span data-ttu-id="31816-147">Si usa procedimientos almacenados para configurar la distribución, utilice `sp_adddistpublisher` para asociar los publicadores remotos al distribuidor.</span><span class="sxs-lookup"><span data-stu-id="31816-147">If you are using stored procedures to configure distribution, use `sp_adddistpublisher` to associate the remote publishers with the distributor.</span></span> <span data-ttu-id="31816-148">Si *@login* y *@password* se usaron para el publicador original, especifique los mismos valores para cada al agregar los hosts de la réplica secundaria como publicadores.</span><span class="sxs-lookup"><span data-stu-id="31816-148">If *@login* and *@password* were used for the original publisher, specify the same values for each when you add the secondary replica hosts as publishers.</span></span>  
  
```sql
EXEC sys.sp_adddistpublisher  
    @publisher = 'AGSecondaryReplicaHost',  
    @distribution_db = 'distribution',  
    @working_directory = '\\MyReplShare\WorkingDir',  
    @login = 'MyPubLogin',  
    @password = '**Strong password for publisher**';  
```  
  
 <span data-ttu-id="31816-149">En cada host de réplica secundaria, configure la distribución.</span><span class="sxs-lookup"><span data-stu-id="31816-149">At each secondary replica host, configure distribution.</span></span> <span data-ttu-id="31816-150">Identifique el distribuidor del publicador original como distribuidor remoto.</span><span class="sxs-lookup"><span data-stu-id="31816-150">Identify the distributor of the original publisher as the remote distributor.</span></span> <span data-ttu-id="31816-151">Use la misma contraseña que se utiliza al ejecutar `sp_adddistributor` originalmente en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="31816-151">Use the same password as that used when `sp_adddistributor` was run originally at the distributor.</span></span> <span data-ttu-id="31816-152">Si se usan procedimientos almacenados para configurar la distribución, el *@password* parámetro de `sp_adddistributor` se utiliza para especificar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="31816-152">If stored procedures are being used to configure distribution, the *@password* parameter of `sp_adddistributor` is used to specify the password.</span></span>  
  
```sql
EXEC sp_adddistributor   
    @distributor = 'MyDistributor',  
    @password = '**Strong password for distributor**';  
```  
  
 <span data-ttu-id="31816-153">En cada host de réplica secundaria, asegúrese de que los suscriptores de inserción de publicaciones de la base de datos aparezcan como servidores vinculados.</span><span class="sxs-lookup"><span data-stu-id="31816-153">At each secondary replica host, make sure that the push subscribers of the database publications appear as linked servers.</span></span> <span data-ttu-id="31816-154">Si se emplean procedimientos almacenados para configurar los publicadores remotos, use `sp_addlinkedserver` para agregar los suscriptores (si todavía no están presentes) como servidores vinculados para los publicadores.</span><span class="sxs-lookup"><span data-stu-id="31816-154">If stored procedures are being used to configure the remote publishers, use `sp_addlinkedserver` to add the subscribers (if not already present) as linked servers to the publishers.</span></span>  
  
```sql
EXEC sys.sp_addlinkedserver   
    @server = 'MySubscriber';  
```  
  
##  <a name="5-redirect-the-original-publisher-to-the-ag-listener-name"></a><a name="step5"></a> <span data-ttu-id="31816-155">5. Redirigir el publicador original al nombre del agente de escucha</span><span class="sxs-lookup"><span data-stu-id="31816-155">5. Redirect the Original Publisher to the AG Listener Name</span></span>  
 <span data-ttu-id="31816-156">En el distribuidor, en la base de datos de distribución, ejecute el procedimiento almacenado `sp_redirect_publisher` para asociar el publicador original y la base de datos publicada al nombre del agente de escucha del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="31816-156">At the distributor, in the distribution database, run the stored procedure `sp_redirect_publisher` to associate the original publisher and the published database with the availability group listener name of the availability group.</span></span>  
  
```sql
USE distribution;  
GO  
EXEC sys.sp_redirect_publisher   
@original_publisher = 'MyPublisher',  
    @publisher_db = 'MyPublishedDB',  
    @redirected_publisher = 'MyAGListenerName';  
```  
  
##  <a name="6-run-the-replication-validation-stored-procedure-to-verify-the-configuration"></a><a name="step6"></a> <span data-ttu-id="31816-157">6. Ejecutar el procedimiento almacenado de validación de la replicación para comprobar la configuración</span><span class="sxs-lookup"><span data-stu-id="31816-157">6. Run the Replication Validation Stored Procedure to Verify the Configuration</span></span>  
 <span data-ttu-id="31816-158">En el distribuidor, en la base de datos de distribución, ejecute el procedimiento almacenado `sp_validate_replica_hosts_as_publishers` para comprobar que ahora todos los hosts de la réplica se configuran para servir como publicadores de la base de datos publicada.</span><span class="sxs-lookup"><span data-stu-id="31816-158">At the distributor, in the distribution database, run the stored procedure `sp_validate_replica_hosts_as_publishers` to verify that all replica hosts are now configured to serve as publishers for the published database.</span></span>  
  
```sql
USE distribution;  
GO  
DECLARE @redirected_publisher sysname;  
EXEC sys.sp_validate_replica_hosts_as_publishers  
    @original_publisher = 'MyPublisher',  
    @publisher_db = 'MyPublishedDB',  
    @redirected_publisher = @redirected_publisher output;  
```  
  
 <span data-ttu-id="31816-159">El procedimiento almacenado `sp_validate_replica_hosts_as_publishers` se debe ejecutar desde un inicio de sesión con autorización suficiente en cada host de réplica del grupo de disponibilidad para consultar información acerca del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="31816-159">The stored procedure `sp_validate_replica_hosts_as_publishers` should be run from a login with sufficient authorization at each availability group replica host to query for information about the availability group.</span></span> <span data-ttu-id="31816-160">A diferencia `sp_validate_redirected_publisher` de, usa las credenciales del autor de la llamada y no utiliza el inicio de sesión que se conserva en msdb. DBO. MSdistpublishers para conectarse a las réplicas del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="31816-160">Unlike `sp_validate_redirected_publisher`, it uses the credentials of the caller and does not use the login retained in msdb.dbo.MSdistpublishers to connect to the availability group replicas.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31816-161">`sp_validate_replica_hosts_as_publishers` producirá el error siguiente al validar los hosts de réplica secundaria que no permiten el acceso de lectura o requieren especificar la intención de lectura.</span><span class="sxs-lookup"><span data-stu-id="31816-161">`sp_validate_replica_hosts_as_publishers` will fail with the following error when validating secondary replica hosts that do not allow read access, or require read intent to be specified.</span></span>  
>   
>  <span data-ttu-id="31816-162">Mensaje 21899, nivel 11, estado 1, procedimiento `sp_hadr_verify_subscribers_at_publisher`, línea 109</span><span class="sxs-lookup"><span data-stu-id="31816-162">Msg 21899, Level 11, State 1, Procedure `sp_hadr_verify_subscribers_at_publisher`, Line 109</span></span>  
>   
>  <span data-ttu-id="31816-163">La consulta en el publicador redireccionado "MyReplicaHostName" para determinar si hay entradas de sysserver para los suscriptores del publicador original "MyOriginalPublisher" no se ha podido realizar por el error "976", mensaje de error "Error 976, Level 14, State 1, Message: La base de datos de destino "MyPublishedDB" participa en un grupo de disponibilidad y actualmente no es accesible para las consultas.</span><span class="sxs-lookup"><span data-stu-id="31816-163">The query at the redirected publisher 'MyReplicaHostName' to determine whether there were sysserver entries for the subscribers of the original publisher 'MyOriginalPublisher' failed with error '976', error message 'Error 976, Level 14, State 1, Message: The target database, 'MyPublishedDB', is participating in an availability group and is currently not accessible for queries.</span></span> <span data-ttu-id="31816-164">El movimiento de datos se ha suspendido o la réplica de disponibilidad no está habilitada para el acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="31816-164">Either data movement is suspended or the availability replica is not enabled for read access.</span></span> <span data-ttu-id="31816-165">Para permitir el acceso de solo lectura a esta y a otras bases de datos del grupo de disponibilidad, habilite el acceso de lectura en una o varias réplicas de disponibilidad secundarias del grupo.</span><span class="sxs-lookup"><span data-stu-id="31816-165">To allow read-only access to this and other databases in the availability group, enable read access to one or more secondary availability replicas in the group.</span></span>  <span data-ttu-id="31816-166">Para obtener más información, vea la instrucción `ALTER AVAILABILITY GROUP` en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]'.</span><span class="sxs-lookup"><span data-stu-id="31816-166">For more information, see the `ALTER AVAILABILITY GROUP` statement in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.'.</span></span>  
>   
>  <span data-ttu-id="31816-167">Se encontraron uno o varios errores de validación del publicador para el host de réplica 'MyReplicaHostName'.</span><span class="sxs-lookup"><span data-stu-id="31816-167">One or more publisher validation errors were encountered for replica host 'MyReplicaHostName'.</span></span>  
  
 <span data-ttu-id="31816-168">Este es el comportamiento esperado.</span><span class="sxs-lookup"><span data-stu-id="31816-168">This is expected behavior.</span></span> <span data-ttu-id="31816-169">Debe comprobar la presencia de las entradas del servidor del suscriptor en estos host de réplica secundaria consultando las entradas de sysserver directamente en el host.</span><span class="sxs-lookup"><span data-stu-id="31816-169">You must verify the presence of the subscriber server entries at these secondary replica hosts by querying for the sysserver entries directly at the host.</span></span>  
  
##  <a name="7-add-the-original-publisher-to-replication-monitor"></a><a name="step7"></a> <span data-ttu-id="31816-170">7. Agregar el publicador original al Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="31816-170">7. Add the Original Publisher to Replication Monitor</span></span>  
 <span data-ttu-id="31816-171">En cada réplica del grupo de disponibilidad, agregue el publicador original al Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="31816-171">At each availability group replica, add the original publisher to Replication Monitor.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="31816-172">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="31816-172">Related Tasks</span></span>  
 <span data-ttu-id="31816-173">**Replicación**</span><span class="sxs-lookup"><span data-stu-id="31816-173">**Replication**</span></span>  
  
-   [<span data-ttu-id="31816-174">Mantener una base de datos de publicación AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31816-174">Maintaining an AlwaysOn Publication Database &#40;SQL Server&#41;</span></span>](maintaining-an-always-on-publication-database-sql-server.md)  
  
-   [<span data-ttu-id="31816-175">Replicación, Change Tracking, captura de datos modificados y Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31816-175">Replication, Change Tracking, Change Data Capture, and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replicate-track-change-data-capture-always-on-availability.md)  
  
-   [<span data-ttu-id="31816-176">Preguntas más frecuentes para administradores de replicación</span><span class="sxs-lookup"><span data-stu-id="31816-176">Replication Administration FAQ</span></span>](../../../relational-databases/replication/administration/frequently-asked-questions-for-replication-administrators.md)  
  
 <span data-ttu-id="31816-177">**Para crear y configurar un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="31816-177">**To create and configure an availability group**</span></span>  
  
-   [<span data-ttu-id="31816-178">Usar el Asistente para grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="31816-178">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="31816-179">Usar el cuadro de diálogo Nuevo grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="31816-179">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="31816-180">Crear un grupo de disponibilidad &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="31816-180">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="31816-181">Crear un grupo de disponibilidad &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="31816-181">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="31816-182">Especificar la dirección URL del punto de conexión al agregar o modificar una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31816-182">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="31816-183">Cree un extremo de creación de reflejo de la base de datos para Grupos de disponibilidad AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="31816-183">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="31816-184">Combinar una réplica secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31816-184">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31816-185">Preparar manualmente una base de datos secundaria para un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31816-185">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31816-186">Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31816-186">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31816-187">Crear o configurar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31816-187">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="31816-188">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31816-188">See Also</span></span>  
 <span data-ttu-id="31816-189">[Requisitos previos, restricciones y recomendaciones para el SQL Server de &#40;de Grupos de disponibilidad AlwaysOn&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="31816-189">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="31816-190">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="31816-190">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="31816-191">[Grupos de disponibilidad AlwaysOn: interoperabilidad (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="31816-191">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 [<span data-ttu-id="31816-192">Replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="31816-192">SQL Server Replication</span></span>](../../../relational-databases/replication/sql-server-replication.md)  
