---
title: Permitir que un extremo de creación de reflejo de la base de datos use certificados para las conexiones salientes (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- certificates [SQL Server], database mirroring
- outbound connections [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 464c9096-10d6-4c5e-8bb1-19acba27ad9e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f380f268f8d0f8d033db9c28f83d066d3f134571
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663680"
---
# <a name="allow-a-database-mirroring-endpoint-to-use-certificates-for-outbound-connections-transact-sql"></a><span data-ttu-id="4dae3-102">Permitir que un extremo de creación de reflejo de la base de datos utilice certificados para las conexiones salientes (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4dae3-102">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections (Transact-SQL)</span></span>
  <span data-ttu-id="4dae3-103">En este tema se describen los pasos necesarios para configurar instancias de servidor que utilicen certificados para autenticar conexiones salientes en la creación de un reflejo de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4dae3-103">This topic describes the steps for configuring server instances to use certificates to authenticate outbound connections for database mirroring.</span></span> <span data-ttu-id="4dae3-104">La configuración de conexiones salientes se debe realizar antes de que se puedan configurar conexiones entrantes.</span><span class="sxs-lookup"><span data-stu-id="4dae3-104">Outbound connection configuration must be done before you can set up inbound connections.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4dae3-105">Todas las conexiones de creación de reflejo en una instancia de servidor utilizan un único extremo de reflejo de la base de datos; debe especificar el método de autenticación de la instancia de servidor cuando cree el extremo.</span><span class="sxs-lookup"><span data-stu-id="4dae3-105">All mirroring connections on a server instance use a single database mirroring endpoint, and you must specify the authentication method of the server instance when you create the endpoint.</span></span>  
  
 <span data-ttu-id="4dae3-106">El proceso de configuración de conexiones salientes implica los siguientes pasos generales:</span><span class="sxs-lookup"><span data-stu-id="4dae3-106">The process of configuring outbound connections, involves the following general steps:</span></span>  
  
1.  <span data-ttu-id="4dae3-107">En la base de datos **master** , cree una clave maestra de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4dae3-107">In the **master** database, create a database Master Key.</span></span>  
  
2.  <span data-ttu-id="4dae3-108">En la base de datos **maestra** , cree un certificado cifrado en la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="4dae3-108">In the **master** database, create an encrypted certificate on the server instance.</span></span>  
  
3.  <span data-ttu-id="4dae3-109">Cree un extremo para la instancia de servidor utilizando su certificado.</span><span class="sxs-lookup"><span data-stu-id="4dae3-109">Create an endpoint for the server instance using its certificate.</span></span>  
  
4.  <span data-ttu-id="4dae3-110">Realice una copia de seguridad del certificado en un archivo. A continuación, cópiela de forma segura a los demás sistemas.</span><span class="sxs-lookup"><span data-stu-id="4dae3-110">Back up the certificate to a file and securely copy it to the other system or systems.</span></span>  
  
 <span data-ttu-id="4dae3-111">Debe completar estos pasos para cada asociado y el testigo, si existe.</span><span class="sxs-lookup"><span data-stu-id="4dae3-111">You must complete these steps for each partner and the witness, if there is one.</span></span>  
  
 <span data-ttu-id="4dae3-112">En el siguiente procedimiento se describen estos pasos detalladamente.</span><span class="sxs-lookup"><span data-stu-id="4dae3-112">The following procedure describes these steps in detail.</span></span> <span data-ttu-id="4dae3-113">Para cada paso, el procedimiento proporciona un ejemplo para configurar una instancia del servidor en un sistema denominado HOST_A.</span><span class="sxs-lookup"><span data-stu-id="4dae3-113">For each step, the procedure provides an example for configuring a server instance on a system named HOST_A.</span></span> <span data-ttu-id="4dae3-114">En la sección Ejemplo anexa se muestran los mismos pasos para otra instancia del servidor en un sistema denominado HOST_B.</span><span class="sxs-lookup"><span data-stu-id="4dae3-114">The accompanying Example section demonstrates the same steps for another server instance on a system named HOST_B.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="4dae3-115">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="4dae3-115">Procedure</span></span>  
  
#### <a name="to-configure-server-instances-for-outbound-mirroring-connections-on-host_a"></a><span data-ttu-id="4dae3-116">Para configurar instancias del servidor para conexiones salientes de creación de reflejo (en HOST_A)</span><span class="sxs-lookup"><span data-stu-id="4dae3-116">To configure server instances for outbound mirroring connections (On HOST_A)</span></span>  
  
1.  <span data-ttu-id="4dae3-117">En la base de datos **master** , cree la clave maestra de la base de datos si no existe ninguna.</span><span class="sxs-lookup"><span data-stu-id="4dae3-117">On the **master** database, create the database Master Key, if none exists.</span></span> <span data-ttu-id="4dae3-118">Para ver las claves existentes en una base de datos, use la vista de catálogo [sys.symmetric_keys](/sql/relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="4dae3-118">To view the existing keys for a database, use the [sys.symmetric_keys](/sql/relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql) catalog view.</span></span>  
  
     <span data-ttu-id="4dae3-119">Para crear la clave maestra de la base de datos, utilice el siguiente comando de [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4dae3-119">To create the database Master Key, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command:</span></span>  
  
    ```  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<1_Strong_Password!>';  
    GO  
    ```  
  
     <span data-ttu-id="4dae3-120">Utilice una contraseña segura única y regístrela en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="4dae3-120">Use a unique, strong password, and record it in a safe place.</span></span>  
  
     <span data-ttu-id="4dae3-121">Para obtener más información, vea [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) y [Crear la clave maestra de una base de datos](../../relational-databases/security/encryption/create-a-database-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="4dae3-121">For more information, see [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) and [Create a Database Master Key](../../relational-databases/security/encryption/create-a-database-master-key.md).</span></span>  
  
2.  <span data-ttu-id="4dae3-122">En la base de datos **maestra** , cree un certificado cifrado en la instancia de servidor con el fin de utilizarlo en las conexiones salientes para la creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4dae3-122">In the **master** database, create an encrypted certificate on the server instance to use for its outbound connections for database mirroring.</span></span>  
  
     <span data-ttu-id="4dae3-123">Por ejemplo, para crear un certificado para el sistema HOST_A.</span><span class="sxs-lookup"><span data-stu-id="4dae3-123">For example, to create a certificate for the HOST_A system.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4dae3-124">Si piensa usar el certificado durante más de un año, especifique la fecha de vencimiento en hora UTC utilizando la opción EXPIRY_DATE en la instrucción CREATE CERTIFICATE.</span><span class="sxs-lookup"><span data-stu-id="4dae3-124">If you intend to use the certificate for more than one year, specify the expiry date in UTC time by using the EXPIRY_DATE option in your CREATE CERTIFICATE statement.</span></span> <span data-ttu-id="4dae3-125">Además, se recomienda utilizar SQL Server Management Studio para crear una regla de administración basada en directivas que le notifique la fecha de expiración de los certificados.</span><span class="sxs-lookup"><span data-stu-id="4dae3-125">Also, we recommend that you use SQL Server Management Studio to create a Policy-Based Management rule to alert you when your certificates are expiring.</span></span> <span data-ttu-id="4dae3-126">Mediante el cuadro de diálogo **Crear nueva condición** de Administración de directivas, cree esta regla en el campo **@ExpirationDate** de la faceta **Certificado** .</span><span class="sxs-lookup"><span data-stu-id="4dae3-126">Using the Policy Management **Create New Condition** dialog box, create this rule on the **@ExpirationDate** field of the **Certificate** facet.</span></span> <span data-ttu-id="4dae3-127">Para obtener más información, vea [Administrar servidores mediante administración basada en directivas](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md) y [Proteger SQL Server](../../relational-databases/security/securing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4dae3-127">For more information, see [Administer Servers by Using Policy-Based Management](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md) and [Securing SQL Server](../../relational-databases/security/securing-sql-server.md).</span></span>  
  
    ```  
    USE master;  
    CREATE CERTIFICATE HOST_A_cert   
       WITH SUBJECT = 'HOST_A certificate for database mirroring',   
       EXPIRY_DATE = '11/30/2013';  
    GO  
    ```  
  
     <span data-ttu-id="4dae3-128">Para obtener más información, vea [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4dae3-128">For more information, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="4dae3-129">Para ver los certificados de la base de datos **maestra** , puede usar las siguientes instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4dae3-129">To view the certificates in the **master** database, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    SELECT * FROM sys.certificates;  
    ```  
  
     <span data-ttu-id="4dae3-130">Para obtener más información, vea [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4dae3-130">For more information, see [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span></span>  
  
3.  <span data-ttu-id="4dae3-131">Asegúrese de que el extremo de creación de reflejo de la base de datos existe en cada una de las instancias de servidor.</span><span class="sxs-lookup"><span data-stu-id="4dae3-131">Ensure that the database mirroring endpoint exist on each of the server instances.</span></span>  
  
     <span data-ttu-id="4dae3-132">Si ya existe un extremo de creación de reflejo de la base de datos para la instancia de servidor, debe volver a utilizar dicho extremo para las demás sesiones que establezca en la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="4dae3-132">If a database mirroring endpoint already exists for the server instance, you should reuse that endpoint for any other sessions you establish on the server instance.</span></span> <span data-ttu-id="4dae3-133">Para determinar si existe un extremo de creación de reflejo de la base de datos en una instancia de servidor y ver su configuración, utilice la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="4dae3-133">To determine whether a database mirroring endpoint exists on a server instance and to view its configuration, use the following statement:</span></span>  
  
    ```  
    SELECT name, role_desc, state_desc, connection_auth_desc, encryption_algorithm_desc   
       FROM sys.database_mirroring_endpoints;  
    ```  
  
     <span data-ttu-id="4dae3-134">Si no existe ningún extremo, cree uno que utilice este certificado en las conexiones salientes y las credenciales del certificado en la comprobación del otro sistema.</span><span class="sxs-lookup"><span data-stu-id="4dae3-134">If no endpoint exists, create an endpoint that uses this certificate for outbound connections and that uses the certificate's credentials for verification on the other system.</span></span> <span data-ttu-id="4dae3-135">Se trata de un extremo para todo el servidor que utilizan todas las sesiones de creación de reflejo en las que participa la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="4dae3-135">This is a server-wide endpoint that is used by all mirroring sessions in which the server instance participates.</span></span>  
  
     <span data-ttu-id="4dae3-136">Por ejemplo, para crear un extremo de creación de reflejo para la instancia del servidor de ejemplo en HOST_A.</span><span class="sxs-lookup"><span data-stu-id="4dae3-136">For example, to create a mirroring endpoint for the example server instance on HOST_A.</span></span>  
  
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
  
     <span data-ttu-id="4dae3-137">Para obtener más información, vea [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4dae3-137">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
4.  <span data-ttu-id="4dae3-138">Realice una copia de seguridad del certificado y cópiela en el otro sistema (o en los otros sistemas).</span><span class="sxs-lookup"><span data-stu-id="4dae3-138">Back up the certificate and copy it to the other system or systems.</span></span> <span data-ttu-id="4dae3-139">Esto es necesario para configurar conexiones entrantes en el otro sistema.</span><span class="sxs-lookup"><span data-stu-id="4dae3-139">This is necessary in order to configure inbound connections on the other system.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_A_cert TO FILE = 'C:\HOST_A_cert.cer';  
    GO  
    ```  
  
     <span data-ttu-id="4dae3-140">Para obtener más información, vea [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4dae3-140">For more information, see [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="4dae3-141">Copie este certificado mediante el método seguro que elija.</span><span class="sxs-lookup"><span data-stu-id="4dae3-141">Copy this certificate using any secure method you choose.</span></span> <span data-ttu-id="4dae3-142">Tenga mucho cuidado de mantener todos sus certificados protegidos.</span><span class="sxs-lookup"><span data-stu-id="4dae3-142">Be extremely careful to keep all of your certificates secure.</span></span>  
  
 <span data-ttu-id="4dae3-143">El código de ejemplo de los pasos anteriores configura conexiones salientes en HOST_A.</span><span class="sxs-lookup"><span data-stu-id="4dae3-143">The example code in the preceding steps configure outbound connections on HOST_A.</span></span>  
  
 <span data-ttu-id="4dae3-144">Ahora tiene que seguir los pasos de salida equivalentes para HOST_B.</span><span class="sxs-lookup"><span data-stu-id="4dae3-144">You now need to perform the equivalent outbound steps for HOST_B.</span></span> <span data-ttu-id="4dae3-145">Estos pasos se ilustran en la siguiente sección Ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4dae3-145">These steps are illustrated in the following Example section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4dae3-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4dae3-146">Example</span></span>  
 <span data-ttu-id="4dae3-147">En el siguiente ejemplo se muestra la configuración de HOST_B para conexiones salientes.</span><span class="sxs-lookup"><span data-stu-id="4dae3-147">The following example demonstrates configuring HOST_B for outbound connections.</span></span>  
  
```  
USE master;  
--Create the database Master Key, if needed.  
CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<Strong_Password_#2>';  
GO  
-- Make a certifcate on HOST_B server instance.  
CREATE CERTIFICATE HOST_B_cert   
   WITH SUBJECT = 'HOST_B certificate for database mirroring',   
   EXPIRY_DATE = '11/30/2013';  
GO  
--Create a mirroring endpoint for the server instance on HOST_B.  
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
--Backup HOST_B certificate.  
BACKUP CERTIFICATE HOST_B_cert TO FILE = 'C:\HOST_B_cert.cer';  
GO   
--Using any secure copy method, copy C:\HOST_B_cert.cer to HOST_A.  
```  
  
 <span data-ttu-id="4dae3-148">Copie el certificado en el otro sistema mediante el método seguro que elija.</span><span class="sxs-lookup"><span data-stu-id="4dae3-148">Copy the certificate to the other system using any secure method you choose.</span></span> <span data-ttu-id="4dae3-149">Tenga mucho cuidado de mantener todos sus certificados protegidos.</span><span class="sxs-lookup"><span data-stu-id="4dae3-149">Be extremely careful to keep all of your certificates secure.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4dae3-150">Después de configurar conexiones salientes, debe configurar conexiones entrantes en cada instancia de servidor para la otra instancia (o instancias) de servidor.</span><span class="sxs-lookup"><span data-stu-id="4dae3-150">After you set up outbound connections, you must configure inbound connections on each server instance for the other server instance or instances.</span></span> <span data-ttu-id="4dae3-151">Para obtener más información, vea [Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones entrantes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="4dae3-151">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
 <span data-ttu-id="4dae3-152">Para obtener información sobre la creación de una base de datos reflejada, incluido un ejemplo de Transact-SQL, vea [Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4dae3-152">For information on creating a mirror database, including a Transact-SQL example, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="4dae3-153">Para obtener un ejemplo de Transact-SQL sobre cómo establecer una sesión en modo de alto rendimiento, vea [Ejemplo: configurar la creación de reflejo de la base de datos mediante certificados &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="4dae3-153">For a Transact-SQL example of establishing a high-performance mode session, see [Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4dae3-154">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4dae3-154">.NET Framework Security</span></span>  
 <span data-ttu-id="4dae3-155">A menos que garantice que su red es segura, se recomienda utilizar el cifrado para las conexiones de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4dae3-155">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span>  
  
 <span data-ttu-id="4dae3-156">Cuando copie un certificado en otro sistema, utilice un método de copia seguro.</span><span class="sxs-lookup"><span data-stu-id="4dae3-156">When copying a certificate to another system, use a secure copy method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dae3-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4dae3-157">See Also</span></span>  
 <span data-ttu-id="4dae3-158">[Elegir un algoritmo de cifrado](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="4dae3-158">[Choose an Encryption Algorithm](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span></span>  
 <span data-ttu-id="4dae3-159">[Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4dae3-159">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="4dae3-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4dae3-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="4dae3-161">[Ejemplo: configurar la creación de reflejo de la base de datos mediante certificados &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="4dae3-161">[Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md) </span></span>  
 <span data-ttu-id="4dae3-162">[El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4dae3-162">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="4dae3-163">[Solucionar problemas de configuración de creación de reflejo de la base de datos &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4dae3-163">[Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md) </span></span>  
 [<span data-ttu-id="4dae3-164">Establecer una base de datos reflejada cifrada</span><span class="sxs-lookup"><span data-stu-id="4dae3-164">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
  
