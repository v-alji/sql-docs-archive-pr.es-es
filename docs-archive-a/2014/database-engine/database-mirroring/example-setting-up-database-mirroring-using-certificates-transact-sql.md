---
title: 'Ejemplo: configurar la creación de reflejo de la base de datos mediante certificados (Transact-SQL) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- certificates [SQL Server], database mirroring
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: df489ecd-deee-465c-a26a-6d1bef6d7b66
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea87e2de984107c5a0fda6eb2629ee5cfd197841
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751469"
---
# <a name="example-setting-up-database-mirroring-using-certificates-transact-sql"></a><span data-ttu-id="2b6e9-102">Ejemplo: configurar la creación de reflejo de la base de datos con certificados (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2b6e9-102">Example: Setting Up Database Mirroring Using Certificates (Transact-SQL)</span></span>
  <span data-ttu-id="2b6e9-103">En este ejemplo se muestran todos los pasos necesarios para crear una sesión de creación de reflejo de la base de datos mediante la autenticación basada en certificados.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-103">This example shows all the stages required to create a database mirroring session using certificate-based authentication.</span></span> <span data-ttu-id="2b6e9-104">En los ejemplos descritos en este tema se utiliza [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b6e9-104">The examples in this topic use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2b6e9-105">A menos que garantice que su red es segura, se recomienda utilizar el cifrado para las conexiones de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-105">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span>  
  
 <span data-ttu-id="2b6e9-106">Cuando copie un certificado en otro sistema, utilice un método de copia seguro.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-106">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="2b6e9-107">Tenga mucho cuidado de mantener todos sus certificados protegidos.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-107">Be extremely careful to keep all of your certificates secure.</span></span>  
  
##  <a name="example"></a><a name="ExampleH2"></a> <span data-ttu-id="2b6e9-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b6e9-108">Example</span></span>  
 <span data-ttu-id="2b6e9-109">En el ejemplo siguiente se muestra lo que se debe hacer en un asociado que reside en el HOST_A.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-109">The following example demonstrates what must be done on one partner that resides on HOST_A.</span></span> <span data-ttu-id="2b6e9-110">En este ejemplo, los dos asociados son las instancias de servidor predeterminadas en tres equipos.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-110">In this example, the two partners are the default server instances on three computer systems.</span></span> <span data-ttu-id="2b6e9-111">Las dos instancias de servidor se ejecutan en dominios de Windows que no son de confianza, por lo que se requiere la autenticación basada en certificados.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-111">The two server instances run in nontrusted Windows domains, so certificate-based authentication is required.</span></span>  
  
 <span data-ttu-id="2b6e9-112">HOST_A adopta el rol principal inicial y HOST_B adopta el rol reflejado.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-112">The initial principal role is taken by HOST_A, and the mirror role is taken by HOST_B.</span></span>  
  
 <span data-ttu-id="2b6e9-113">Configurar la creación de reflejo de la base de datos mediante certificados implica cuatro fases generales. En este ejemplo se muestran tres de ellas: 1, 2 y 4.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-113">Setting up database mirroring using certificates involves four general stages, of which three stages-1, 2, and 4-are demonstrated by this example.</span></span> <span data-ttu-id="2b6e9-114">Estas fases son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b6e9-114">These stages are as follows:</span></span>  
  
1.  [<span data-ttu-id="2b6e9-115">Configurar conexiones salientes</span><span class="sxs-lookup"><span data-stu-id="2b6e9-115">Configuring Outbound Connections</span></span>](#ConfiguringOutboundConnections)  
  
     <span data-ttu-id="2b6e9-116">En este ejemplo muestran los pasos para:</span><span class="sxs-lookup"><span data-stu-id="2b6e9-116">This example shows the steps for:</span></span>  
  
    1.  <span data-ttu-id="2b6e9-117">Configurar Host_A para conexiones salientes.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-117">Configuring Host_A for outbound connections.</span></span>  
  
    2.  <span data-ttu-id="2b6e9-118">Configurar Host_B para conexiones salientes.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-118">Configuring Host_B for outbound connections.</span></span>  
  
     <span data-ttu-id="2b6e9-119">Para obtener más información sobre esta fase de configuración de la creación de reflejo de la base de datos, vea [Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones salientes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="2b6e9-119">For information about this stage of setting up database mirroring, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
2.  [<span data-ttu-id="2b6e9-120">Configurar conexiones entrantes</span><span class="sxs-lookup"><span data-stu-id="2b6e9-120">Configuring Inbound Connections</span></span>](#ConfigureInboundConnections)  
  
     <span data-ttu-id="2b6e9-121">En este ejemplo muestran los pasos para:</span><span class="sxs-lookup"><span data-stu-id="2b6e9-121">This example shows the steps for:</span></span>  
  
    1.  <span data-ttu-id="2b6e9-122">Configurar Host_A para conexiones entrantes.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-122">Configuring Host_A for inbound connections.</span></span>  
  
    2.  <span data-ttu-id="2b6e9-123">Configurar Host_B para conexiones entrantes.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-123">Configuring Host_B for inbound connections.</span></span>  
  
     <span data-ttu-id="2b6e9-124">Para obtener más información sobre esta fase de configuración de la creación de reflejo de la base de datos, vea [Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones entrantes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="2b6e9-124">For information about this stage of setting up database mirroring, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
3.  <span data-ttu-id="2b6e9-125">Crear la base de datos reflejada</span><span class="sxs-lookup"><span data-stu-id="2b6e9-125">Creating the Mirror Database</span></span>  
  
     <span data-ttu-id="2b6e9-126">Para obtener más información sobre cómo crear una base de datos reflejada, vea [Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2b6e9-126">For information on how to create a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
4.  [<span data-ttu-id="2b6e9-127">Configurar los asociados de creación de reflejo</span><span class="sxs-lookup"><span data-stu-id="2b6e9-127">Configuring the Mirroring Partners</span></span>](#ConfigureMirroringPartners)  
  
###  <a name="configuring-outbound-connections"></a><a name="ConfiguringOutboundConnections"></a> <span data-ttu-id="2b6e9-128">Configurar conexiones salientes</span><span class="sxs-lookup"><span data-stu-id="2b6e9-128">Configuring Outbound Connections</span></span>  
 <span data-ttu-id="2b6e9-129">**Para configurar Host_A para conexiones salientes**</span><span class="sxs-lookup"><span data-stu-id="2b6e9-129">**To configure Host_A for outbound connections**</span></span>  
  
1.  <span data-ttu-id="2b6e9-130">En la base de datos maestra, cree la clave maestra de la base de datos si es necesaria.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-130">On the master database, create the database master key, if needed.</span></span>  
  
    ```  
    USE master;  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<1_Strong_Password!>';  
    GO  
    ```  
  
2.  <span data-ttu-id="2b6e9-131">Cree un certificado para esta instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-131">Make a certificate for this server instance.</span></span>  
  
    ```  
    USE master;  
    CREATE CERTIFICATE HOST_A_cert   
       WITH SUBJECT = 'HOST_A certificate';  
    GO  
    ```  
  
3.  <span data-ttu-id="2b6e9-132">Cree un extremo de creación de reflejo para la instancia de servidor mediante el certificado.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-132">Create a mirroring endpoint for server instance using the certificate.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
       STATE = STARTED  
       AS TCP (  
          LISTENER_PORT=7024  
          , LISTENER_IP = ALL  
       )   
       FOR DATABASE_MIRRORING (   
          AUTHENTICATION = CERTIFICATE HOST_A_cert  
          , ENCRYPTION = REQUIRED ALGORITHM AES  
          , ROLE = ALL  
       );  
    GO  
    ```  
  
4.  <span data-ttu-id="2b6e9-133">Realice una copia de seguridad del certificado HOST_A y cópielo en el otro sistema, HOST_B.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-133">Back up the HOST_A certificate, and copy it to other system, HOST_B.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_A_cert TO FILE = 'C:\HOST_A_cert.cer';  
    GO  
    ```  
  
5.  <span data-ttu-id="2b6e9-134">Utilizando cualquier método de copia seguro, copie C:\HOST_A_cert.cer en HOST_B.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-134">Using any secure copy method, copy C:\HOST_A_cert.cer to HOST_B.</span></span>  
  
 <span data-ttu-id="2b6e9-135">**Para configurar Host_B para conexiones salientes**</span><span class="sxs-lookup"><span data-stu-id="2b6e9-135">**To configure Host_B for outbound connections**</span></span>  
  
1.  <span data-ttu-id="2b6e9-136">En la base de datos maestra, cree la clave maestra de la base de datos si es necesaria.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-136">On the master database, create the database master key, if needed.</span></span>  
  
    ```  
    USE master;  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<Strong_Password_#2>';  
    GO  
    ```  
  
2.  <span data-ttu-id="2b6e9-137">Cree un certificado en la instancia de servidor HOST_B.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-137">Make a certificate on the HOST_B server instance.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_B_cert   
       WITH SUBJECT = 'HOST_B certificate for database mirroring';  
    GO  
    ```  
  
3.  <span data-ttu-id="2b6e9-138">Cree un extremo de creación de reflejo para la instancia de servidor en HOST_B.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-138">Create a mirroring endpoint for the server instance on HOST_B.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
       STATE = STARTED  
       AS TCP (  
          LISTENER_PORT=7024  
          , LISTENER_IP = ALL  
       )   
       FOR DATABASE_MIRRORING (   
          AUTHENTICATION = CERTIFICATE HOST_B_cert  
          , ENCRYPTION = REQUIRED ALGORITHM AES  
          , ROLE = ALL  
       );  
    GO  
    ```  
  
4.  <span data-ttu-id="2b6e9-139">Realice una copia de seguridad del certificado de HOST_B.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-139">Back up HOST_B certificate.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_B_cert TO FILE = 'C:\HOST_B_cert.cer';  
    GO   
    ```  
  
5.  <span data-ttu-id="2b6e9-140">Utilizando cualquier método de copia seguro, copie C:\HOST_B_cert.cer en HOST_A.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-140">Using any secure copy method, copy C:\HOST_B_cert.cer to HOST_A.</span></span>  
  
 <span data-ttu-id="2b6e9-141">Para obtener más información, vea [Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones salientes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="2b6e9-141">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
###  <a name="configuring-inbound-connections"></a><a name="ConfigureInboundConnections"></a> <span data-ttu-id="2b6e9-142">Configurar conexiones entrantes</span><span class="sxs-lookup"><span data-stu-id="2b6e9-142">Configuring Inbound Connections</span></span>  
 <span data-ttu-id="2b6e9-143">**Para configurar Host_A para conexiones entrantes**</span><span class="sxs-lookup"><span data-stu-id="2b6e9-143">**To configure Host_A for inbound connections**</span></span>  
  
1.  <span data-ttu-id="2b6e9-144">Cree un inicio de sesión en HOST_A para HOST_B.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-144">Create a login on HOST_A for HOST_B.</span></span>  
  
    ```  
    USE master;  
    CREATE LOGIN HOST_B_login WITH PASSWORD = '1Sample_Strong_Password!@#';  
    GO  
    ```  
  
2.  <span data-ttu-id="2b6e9-145">Cree un usuario para dicho inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-145">--Create a user for that login.</span></span>  
  
    ```  
    CREATE USER HOST_B_user FOR LOGIN HOST_B_login;  
    GO  
    ```  
  
3.  <span data-ttu-id="2b6e9-146">Asocie el certificado al usuario.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-146">--Associate the certificate with the user.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_B_cert  
       AUTHORIZATION HOST_B_user  
       FROM FILE = 'C:\HOST_B_cert.cer'  
    GO  
    ```  
  
4.  <span data-ttu-id="2b6e9-147">Conceda el permiso CONNECT para el inicio de sesión al extremo de creación de reflejo remoto.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-147">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_B_login];  
    GO  
    ```  
  
 <span data-ttu-id="2b6e9-148">**Para configurar Host_B para conexiones entrantes**</span><span class="sxs-lookup"><span data-stu-id="2b6e9-148">**To configure Host_B for inbound connections**</span></span>  
  
1.  <span data-ttu-id="2b6e9-149">Cree un inicio de sesión en HOST_B para HOST_A.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-149">Create a login on HOST_B for HOST_A.</span></span>  
  
    ```  
    USE master;  
    CREATE LOGIN HOST_A_login WITH PASSWORD = '=Sample#2_Strong_Password2';  
    GO  
    ```  
  
2.  <span data-ttu-id="2b6e9-150">Cree un usuario para dicho inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-150">Create a user for that login.</span></span>  
  
    ```  
    CREATE USER HOST_A_user FOR LOGIN HOST_A_login;  
    GO  
    ```  
  
3.  <span data-ttu-id="2b6e9-151">Asocie el certificado al usuario.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-151">Associate the certificate with the user.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_A_cert  
       AUTHORIZATION HOST_A_user  
       FROM FILE = 'C:\HOST_A_cert.cer'  
    GO  
    ```  
  
4.  <span data-ttu-id="2b6e9-152">Conceda el permiso CONNECT para el inicio de sesión al extremo de creación de reflejo remoto.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-152">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_A_login];  
    GO  
    ```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2b6e9-153">Si tiene planeado que la ejecución se realice en modo de alta seguridad con conmutación automática por error, debe repetir los mismos pasos de configuración para configurar el testigo de las conexiones entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-153">If you intend to run in high-safety mode with automatic failover, you must repeat the same setup steps to configure the witness for outbound and inbound connections.</span></span> <span data-ttu-id="2b6e9-154">La configuración de conexiones de entrantes cuando un testigo está implicado requiere configurar inicios de sesión y usuarios para los testigos de los asociados y de los asociados del testigo.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-154">Setting up the inbound connections when a witness is involved requires that you set up logins and users for the witness on both of the partners and for both partners on the witness.</span></span>  
  
 <span data-ttu-id="2b6e9-155">Para obtener más información, vea [Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones entrantes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="2b6e9-155">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
### <a name="creating-the-mirror-database"></a><span data-ttu-id="2b6e9-156">Crear la base de datos reflejada</span><span class="sxs-lookup"><span data-stu-id="2b6e9-156">Creating the Mirror Database</span></span>  
 <span data-ttu-id="2b6e9-157">Para obtener más información sobre cómo crear una base de datos reflejada, vea [Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2b6e9-157">For information on how to create a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
###  <a name="configuring-the-mirroring-partners"></a><a name="ConfigureMirroringPartners"></a> <span data-ttu-id="2b6e9-158">Configurar los asociados de creación de reflejo</span><span class="sxs-lookup"><span data-stu-id="2b6e9-158">Configuring the Mirroring Partners</span></span>  
  
1.  <span data-ttu-id="2b6e9-159">En la instancia del servidor reflejado en HOST_B, establezca la instancia de servidor en HOST_A como asociado (para convertirla en la instancia inicial del servidor principal):</span><span class="sxs-lookup"><span data-stu-id="2b6e9-159">On the mirror server instance on HOST_B, set the server instance on HOST_A as the partner (making it the initial principal server instance).</span></span> <span data-ttu-id="2b6e9-160">Sustituya una dirección de red válida por `TCP://HOST_A.Mydomain.Corp.Adventure-Works``.com:7024`.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-160">Substitute a valid network address for `TCP://HOST_A.Mydomain.Corp.Adventure-Works``.com:7024`.</span></span> <span data-ttu-id="2b6e9-161">Para obtener más información, vea [Especificar una dirección de red de servidor &#40;creación de reflejo de la base de datos&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="2b6e9-161">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
    ```  
    --At HOST_B, set server instance on HOST_A as partner (principal server):  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://HOST_A.Mydomain.Corp.Adventure-Works.com:7024';  
    GO  
    ```  
  
2.  <span data-ttu-id="2b6e9-162">En la instancia del servidor principal en HOST_A, establezca la instancia de servidor en HOST_B como asociado (para convertirla en la instancia inicial del servidor reflejado):</span><span class="sxs-lookup"><span data-stu-id="2b6e9-162">On the principal server instance on HOST_A, set the server instance on HOST_B as the partner (making it the initial mirror server instance).</span></span> <span data-ttu-id="2b6e9-163">Sustituya una dirección de red válida por `TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024`.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-163">Substitute a valid network address for `TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024`.</span></span>  
  
    ```  
    --At HOST_A, set server instance on HOST_B as partner (mirror server).  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024';  
    GO  
    ```  
  
3.  <span data-ttu-id="2b6e9-164">En este ejemplo se considera que la sesión se ejecutará en modo de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-164">This example assumes that the session will be running in high-performance mode.</span></span> <span data-ttu-id="2b6e9-165">Para configurar esta sesión para el modo de alto rendimiento, en la instancia del servidor principal (en HOST_A), establezca la seguridad de la transacción en OFF.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-165">To configure this session for high-performance mode, on the principal server instance (on HOST_A), set transaction safety to OFF.</span></span>  
  
    ```  
    --Change to high-performance mode by turning off transacton safety.  
    ALTER DATABASE AdventureWorks   
        SET PARTNER SAFETY OFF  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="2b6e9-166">Si desea ejecutar en modo de alta seguridad con conmutación automática por error, deje la seguridad de las transacciones establecida en Full (configuración predeterminada) y agregue el testigo lo antes posible después de ejecutar la segunda instrucción set Partner **' *`partner_server`* '** .</span><span class="sxs-lookup"><span data-stu-id="2b6e9-166">If you intend to run in high-safety mode with automatic failover, leave transaction safety set to FULL (the default setting) and add the witness as soon as possible after executing the second SET PARTNER **'*`partner_server`*'** statement.</span></span> <span data-ttu-id="2b6e9-167">Tenga en cuenta que primero se debe configurar el testigo para conexiones salientes y entrantes.</span><span class="sxs-lookup"><span data-stu-id="2b6e9-167">Note that the witness must first be configured for outbound and inbound connections.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2b6e9-168">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="2b6e9-168">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2b6e9-169">Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2b6e9-169">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
-   [<span data-ttu-id="2b6e9-170">Permitir que un punto de conexión de creación de reflejo de la base de datos use certificados para las conexiones entrantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2b6e9-170">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="2b6e9-171">Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones salientes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2b6e9-171">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
-   [<span data-ttu-id="2b6e9-172">Administración de inicios de sesión y trabajos tras la conmutación de roles &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2b6e9-172">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
-   <span data-ttu-id="2b6e9-173">[Administrar los metadatos cuando una base de datos pasa a estar disponible en otra instancia del servidor &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md)</span><span class="sxs-lookup"><span data-stu-id="2b6e9-173">[Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) (SQL Server)</span></span>  
  
-   [<span data-ttu-id="2b6e9-174">Solucionar problemas de configuración de creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2b6e9-174">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](troubleshoot-database-mirroring-configuration-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="2b6e9-175">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b6e9-175">See Also</span></span>  
 <span data-ttu-id="2b6e9-176">[Seguridad de transporte para la creación de reflejo de la base de datos y Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="2b6e9-176">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="2b6e9-177">[Especificar una dirección de red de servidor &#40;creación de reflejo de la base de datos&#41;](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="2b6e9-177">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="2b6e9-178">[El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2b6e9-178">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="2b6e9-179">[Usar certificados para un punto de conexión de creación de reflejo de la base de datos &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="2b6e9-179">[Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md) </span></span>  
 <span data-ttu-id="2b6e9-180">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b6e9-180">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="2b6e9-181">Centro de seguridad para el Motor de base de datos de SQL Server y Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="2b6e9-181">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
