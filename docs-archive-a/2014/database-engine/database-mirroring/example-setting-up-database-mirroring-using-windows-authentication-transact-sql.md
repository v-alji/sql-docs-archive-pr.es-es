---
title: 'Ejemplo: configurar la creación de reflejo de la base de datos mediante la autenticación de Windows (Transact-SQL) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- Windows authentication [SQL Server]
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: 35800769-aede-4aac-b077-0e0e487e302f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95df855e8e41c5937aae02884c71792537eb2bfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663663"
---
# <a name="example-setting-up-database-mirroring-using-windows-authentication-transact-sql"></a><span data-ttu-id="14119-102">Ejemplo: Configurar la creación de reflejo de la base de datos mediante la autenticación de Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="14119-102">Example: Setting Up Database Mirroring Using Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="14119-103">En este ejemplo se muestran todos los pasos necesarios para crear una sesión de creación de reflejo de la base de datos con un testigo mediante la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="14119-103">This example shows all the stages required to create a database mirroring session with a witness using Windows Authentication.</span></span> <span data-ttu-id="14119-104">En los ejemplos descritos en este tema se utiliza [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14119-104">The examples in this topic use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="14119-105">Tenga en cuenta que como alternativa a los pasos que utilizan [!INCLUDE[tsql](../../includes/tsql-md.md)], puede utilizar el Asistente para la configuración de seguridad de la creación de reflejo de bases de datos para configurar la creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="14119-105">Note that as an alternative to using [!INCLUDE[tsql](../../includes/tsql-md.md)] steps, you can use the Configure Database Mirroring Security Wizard for database mirroring setup.</span></span> <span data-ttu-id="14119-106">Para obtener más información, vea [Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="14119-106">For more information, see [Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="14119-107">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="14119-107">Prerequisite</span></span>  
 <span data-ttu-id="14119-108">Este ejemplo utiliza la base de datos de ejemplo **AdventureWorks** , que usa de forma predeterminada un modelo de recuperación simple.</span><span class="sxs-lookup"><span data-stu-id="14119-108">The example uses the **AdventureWorks** sample database, which uses the simple recovery model by default.</span></span> <span data-ttu-id="14119-109">Para utilizar la creación de reflejo de la base de datos con esta base de datos, modifíquela para que utilice el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="14119-109">To use database mirroring with this database, you must alter it to use the full recovery model.</span></span> <span data-ttu-id="14119-110">Para llevarlo a cabo en [!INCLUDE[tsql](../../includes/tsql-md.md)], use la instrucción ALTER DATABASE del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="14119-110">To do this in [!INCLUDE[tsql](../../includes/tsql-md.md)], use the ALTER DATABASE statement, as follows:</span></span>  
  
```  
USE master;  
GO  
ALTER DATABASE AdventureWorks   
SET RECOVERY FULL;  
GO  
```  
  
 <span data-ttu-id="14119-111">Para obtener más información sobre el cambio del modelo de recuperación de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], vea [Ver o cambiar el modelo de recuperación de una base de datos &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="14119-111">For information on changing the recovery model in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
### <a name="permissions"></a><span data-ttu-id="14119-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="14119-112">Permissions</span></span>  
 <span data-ttu-id="14119-113">Necesita el permiso ALTER en la base de datos y el permiso CREATE ENDPOINT, o la pertenencia al rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="14119-113">Requires ALTER permission on the database and CREATE ENDPOINT permission, or membership in the **sysadmin** fixed server role.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14119-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14119-114">Example</span></span>  
 <span data-ttu-id="14119-115">En este ejemplo, dos asociados y el testigo son las instancias de servidor predeterminadas en tres equipos.</span><span class="sxs-lookup"><span data-stu-id="14119-115">In this example, the two partners and the witness are the default server instances on three computer systems.</span></span> <span data-ttu-id="14119-116">Las tres instancias de servidor se ejecutan en el mismo dominio de Windows, pero la cuenta de usuario (usada como cuenta de servicio de inicio) es diferente para la instancia del servidor testigo del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="14119-116">The three server instances run the same Windows domain, but the user account (used as the startup service account) is different for the example's witness server instance.</span></span>  
  
 <span data-ttu-id="14119-117">En la siguiente tabla se muestran de forma resumida los valores utilizados en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="14119-117">The following table summarizes the values used in this example.</span></span>  
  
|<span data-ttu-id="14119-118">Rol de creación de reflejo inicial</span><span class="sxs-lookup"><span data-stu-id="14119-118">Initial mirroring role</span></span>|<span data-ttu-id="14119-119">Sistema host</span><span class="sxs-lookup"><span data-stu-id="14119-119">Host system</span></span>|<span data-ttu-id="14119-120">Cuenta de usuario de dominio</span><span class="sxs-lookup"><span data-stu-id="14119-120">Domain user account</span></span>|  
|----------------------------|-----------------|-------------------------|  
|<span data-ttu-id="14119-121">Principal</span><span class="sxs-lookup"><span data-stu-id="14119-121">Principal</span></span>|<span data-ttu-id="14119-122">PARTNERHOST1</span><span class="sxs-lookup"><span data-stu-id="14119-122">PARTNERHOST1</span></span>|<span data-ttu-id="14119-123">*\<Mydomain>\\<dbousername\>*</span><span class="sxs-lookup"><span data-stu-id="14119-123">*\<Mydomain>\\<dbousername\>*</span></span>|  
|<span data-ttu-id="14119-124">Reflejo</span><span class="sxs-lookup"><span data-stu-id="14119-124">Mirror</span></span>|<span data-ttu-id="14119-125">PARTNERHOST5</span><span class="sxs-lookup"><span data-stu-id="14119-125">PARTNERHOST5</span></span>|<span data-ttu-id="14119-126">*\<Mydomain>\\<dbousername\>*</span><span class="sxs-lookup"><span data-stu-id="14119-126">*\<Mydomain>\\<dbousername\>*</span></span>|  
|<span data-ttu-id="14119-127">Testigo</span><span class="sxs-lookup"><span data-stu-id="14119-127">Witness</span></span>|<span data-ttu-id="14119-128">WITNESSHOST4</span><span class="sxs-lookup"><span data-stu-id="14119-128">WITNESSHOST4</span></span>|<span data-ttu-id="14119-129">*\<Somedomain>\\<witnessuser\>*</span><span class="sxs-lookup"><span data-stu-id="14119-129">*\<Somedomain>\\<witnessuser\>*</span></span>|  
  
1.  <span data-ttu-id="14119-130">Cree un extremo en la instancia del servidor principal (instancia predeterminada en PARTNERHOST1).</span><span class="sxs-lookup"><span data-stu-id="14119-130">Create an endpoint on the principal server instance (default instance on PARTNERHOST1).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=PARTNER)  
    GO  
    --Partners under same domain user; login already exists in master.  
    --Create a login for the witness server instance,  
    --which is running as Somedomain\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [Somedomain\witnessuser] FROM WINDOWS ;  
    GO  
    -- Grant connect permissions on endpoint to login account of witness.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Somedomain\witnessuser];  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
2.  <span data-ttu-id="14119-131">Cree un extremo en la instancia del servidor reflejado (instancia predeterminada en PARTNERHOST5).</span><span class="sxs-lookup"><span data-stu-id="14119-131">Create an endpoint on the mirror server instance (default instance on PARTNERHOST5).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    --Create a login for the witness server instance,  
    --which is running as Somedomain\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [Somedomain\witnessuser] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account of witness.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Somedomain\witnessuser];  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
3.  <span data-ttu-id="14119-132">Cree un extremo en la instancia del servidor testigo (instancia predeterminada en WITNESSHOST4).</span><span class="sxs-lookup"><span data-stu-id="14119-132">Create an endpoint on the witness server instance (default instance on WITNESSHOST4).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=WITNESS)  
    GO  
    --Create a login for the partner server instances,  
    --which are both running as Mydomain\dbousername:  
    USE master ;  
    GO  
    CREATE LOGIN [Mydomain\dbousername] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
4.  <span data-ttu-id="14119-133">Cree la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="14119-133">Create the mirror database.</span></span> <span data-ttu-id="14119-134">Para obtener más información, vea [Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="14119-134">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="14119-135">En la instancia del servidor reflejado en PARTNERHOST5, establezca la instancia de servidor en PARTNERHOST1 como asociado (para convertirla en la instancia del servidor principal inicial).</span><span class="sxs-lookup"><span data-stu-id="14119-135">On the mirror server instance on PARTNERHOST5, set the server instance on PARTNERHOST1 as the partner (making it the initial principal server instance).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET PARTNER =   
        'TCP://PARTNERHOST1.COM:7022'  
    GO  
    ```  
  
6.  <span data-ttu-id="14119-136">En la instancia del servidor principal en PARTNERHOST1, establezca la instancia de servidor en PARTNERHOST5 como asociado (para convertirla en la instancia del servidor reflejado inicial).</span><span class="sxs-lookup"><span data-stu-id="14119-136">On the principal server instance on PARTNERHOST1, set the server instance on PARTNERHOST5 as the partner (making it the initial mirror server instance).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://PARTNERHOST5.COM:7022'  
    GO  
    ```  
  
7.  <span data-ttu-id="14119-137">En el servidor principal, establezca el testigo (que se encuentra en WITNESSHOST4).</span><span class="sxs-lookup"><span data-stu-id="14119-137">On the principal server, set the witness (which is on WITNESSHOST4).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET WITNESS =   
        'TCP://WITNESSHOST4.COM:7022'  
    GO  
    ```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="14119-138">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="14119-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="14119-139">Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="14119-139">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
-   [<span data-ttu-id="14119-140">Iniciar el Asistente para la configuración de seguridad de la creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="14119-140">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
-   [<span data-ttu-id="14119-141">Configurar una base de datos reflejada para usar la propiedad Trustworthy &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="14119-141">Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;</span></span>](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)  
  
-   [<span data-ttu-id="14119-142">Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones salientes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="14119-142">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
-   [<span data-ttu-id="14119-143">Permitir que un punto de conexión de creación de reflejo de la base de datos use certificados para las conexiones entrantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="14119-143">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="14119-144">Ejemplo: Configurar la creación de reflejo de la base de datos con certificados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="14119-144">Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;</span></span>](example-setting-up-database-mirroring-using-certificates-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="14119-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14119-145">See Also</span></span>  
 <span data-ttu-id="14119-146">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14119-146">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="14119-147">[El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="14119-147">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="14119-148">[Seguridad de transporte para la creación de reflejo de la base de datos y Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="14119-148">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="14119-149">[Administrar los metadatos cuando una base de datos pasa a estar disponible en otra instancia del servidor &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) </span><span class="sxs-lookup"><span data-stu-id="14119-149">[Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) </span></span>  
 [<span data-ttu-id="14119-150">Centro de seguridad para el Motor de base de datos de SQL Server y Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="14119-150">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
