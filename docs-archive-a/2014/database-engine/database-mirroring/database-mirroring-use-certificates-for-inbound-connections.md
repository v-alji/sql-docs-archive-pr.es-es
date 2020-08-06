---
title: Permitir que un extremo de creación de reflejo de la base de datos use certificados para las conexiones entrantes (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- certificates [SQL Server], database mirroring
- inbound connections
- database mirroring [SQL Server], security
ms.assetid: 5d48bb98-61f0-4b99-8f1a-b53f831d63d0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c05397dfbd1740293c4b154ace1ed5704cec11a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663681"
---
# <a name="allow-a-database-mirroring-endpoint-to-use-certificates-for-inbound-connections-transact-sql"></a><span data-ttu-id="9bc9a-102">Permitir que un extremo de creación de reflejo de la base de datos utilice certificados para las conexiones entrantes (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9bc9a-102">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections (Transact-SQL)</span></span>
  <span data-ttu-id="9bc9a-103">En este tema se describen los pasos necesarios para configurar instancias del servidor que utilicen certificados para autenticar conexiones entrantes para la creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-103">This topic describes the steps for configuring server instances to use certificates to authenticate inbound connections for database mirroring.</span></span> <span data-ttu-id="9bc9a-104">Antes de poder configurar las conexiones entrantes, deberá configurar las conexiones salientes en cada una de las instancias del servidor.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-104">Before you can set up inbound connections, you must configure outbound connections on each server instance.</span></span> <span data-ttu-id="9bc9a-105">Para obtener más información, vea [Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones salientes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="9bc9a-105">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
 <span data-ttu-id="9bc9a-106">El proceso de configuración de conexiones entrantes implica los siguientes pasos generales:</span><span class="sxs-lookup"><span data-stu-id="9bc9a-106">The process of configuring inbound connections, involves the following general steps:</span></span>  
  
1.  <span data-ttu-id="9bc9a-107">Crear un inicio de sesión para otro sistema.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-107">Create a login for other system.</span></span>  
  
2.  <span data-ttu-id="9bc9a-108">Cree un usuario para dicho inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-108">Create a user for that login.</span></span>  
  
3.  <span data-ttu-id="9bc9a-109">Obtenga el certificado para el extremo de reflejo de la otra instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-109">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
4.  <span data-ttu-id="9bc9a-110">Asociar el certificado al usuario creado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-110">Associate the certificate with the user created in step 2.</span></span>  
  
5.  <span data-ttu-id="9bc9a-111">Conceda el permiso CONNECT para el inicio de sesión para el extremo de reflejo.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-111">Grant CONNECT permission on the login for that mirroring endpoint.</span></span>  
  
 <span data-ttu-id="9bc9a-112">Si existe un testigo, también debe configurar conexiones de entrada para él.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-112">If there is a witness, you must also set up inbound connections for it.</span></span> <span data-ttu-id="9bc9a-113">Esto requiere la configuración de inicios de sesión, usuarios y certificados para el testigo en los dos asociados y viceversa.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-113">This requires setting up logins, users, and certificates for the witness on both of the partners, and vice versa.</span></span>  
  
 <span data-ttu-id="9bc9a-114">En el siguiente procedimiento se describen estos pasos detalladamente.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-114">The following procedure describes these steps in detail.</span></span> <span data-ttu-id="9bc9a-115">Para cada paso, el procedimiento proporciona un ejemplo para configurar una instancia del servidor en un sistema denominado HOST_A.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-115">For each step, the procedure provides an example for configuring a server instance on a system named HOST_A.</span></span> <span data-ttu-id="9bc9a-116">En la sección Ejemplo anexa se muestran los mismos pasos para otra instancia del servidor en un sistema denominado HOST_B.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-116">The accompanying Example section demonstrates the same steps for another server instance on a system named HOST_B.</span></span>  
  
### <a name="to-configure-server-instances-for-inbound-mirroring-connections-on-host_a"></a><span data-ttu-id="9bc9a-117">Para configurar instancias del servidor para conexiones entrantes de creación de reflejo (en HOST_A)</span><span class="sxs-lookup"><span data-stu-id="9bc9a-117">To configure server instances for inbound mirroring connections (on HOST_A)</span></span>  
  
1.  <span data-ttu-id="9bc9a-118">Cree un inicio de sesión para el otro sistema.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-118">Create a login for the other system.</span></span>  
  
     <span data-ttu-id="9bc9a-119">En el siguiente ejemplo se crea un inicio de sesión para el sistema HOST_B en la base de datos **master** de la instancia del servidor de HOST_A; en este ejemplo, el inicio de sesión se denomina `HOST_B_login`.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-119">The following example creates a login for the system, HOST_B, in the **master** database of the server instance on HOST_A; in this example, the login is named `HOST_B_login`.</span></span> <span data-ttu-id="9bc9a-120">Sustituya la contraseña de ejemplo por su propia contraseña.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-120">Substitute a password of your own for the sample password.</span></span>  
  
    ```sql  
    USE master;  
    CREATE LOGIN HOST_B_login   
       WITH PASSWORD = '1Sample_Strong_Password!@#';  
    GO  
    ```  
  
     <span data-ttu-id="9bc9a-121">Para obtener más información, vea [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9bc9a-121">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
     <span data-ttu-id="9bc9a-122">Para ver los inicios de sesión en esta instancia del servidor, puede utilizar la siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9bc9a-122">To view the logins on this server instance, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.server_principals;  
    ```  
  
     <span data-ttu-id="9bc9a-123">Para obtener más información, vea [sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9bc9a-123">For more information, see [sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql).</span></span>  
  
2.  <span data-ttu-id="9bc9a-124">Cree un usuario para dicho inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-124">Create a user for that login.</span></span>  
  
     <span data-ttu-id="9bc9a-125">En el siguiente ejemplo se crea un usuario, `HOST_B_user`, para el inicio de sesión creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-125">The following example creates a user, `HOST_B_user`, for the login created in the preceding step.</span></span>  
  
    ```sql  
    USE master;  
    CREATE USER HOST_B_user FOR LOGIN HOST_B_login;  
    GO  
    ```  
  
     <span data-ttu-id="9bc9a-126">Para obtener más información, vea [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9bc9a-126">For more information, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
     <span data-ttu-id="9bc9a-127">Para ver los usuarios en esta instancia del servidor, puede utilizar la siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9bc9a-127">To view the users on this server instance, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.sysusers;  
    ```  
  
     <span data-ttu-id="9bc9a-128">Para obtener más información, vea [sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9bc9a-128">For more information, see [sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql).</span></span>  
  
3.  <span data-ttu-id="9bc9a-129">Obtenga el certificado para el extremo de reflejo de la otra instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-129">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
     <span data-ttu-id="9bc9a-130">Si todavía no lo ha hecho al configurar las conexiones entrantes, obtenga una copia del certificado para el extremo de creación de reflejo de la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-130">If you have not already done so when configuring outbound connections, obtain a copy of the certificate for the mirroring endpoint of the remote server instance.</span></span> <span data-ttu-id="9bc9a-131">Para ello, realice una copia de seguridad del certificado en esa instancia del servidor como se describe en [Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones salientes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="9bc9a-131">To do this, back up the certificate on that server instance as described in [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span> <span data-ttu-id="9bc9a-132">Cuando copie un certificado en otro sistema, utilice un método de copia seguro.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-132">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="9bc9a-133">Tenga mucho cuidado de mantener todos sus certificados protegidos.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-133">Be extremely careful to keep all of your certificates secure.</span></span>  
  
     <span data-ttu-id="9bc9a-134">Para obtener más información, vea [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9bc9a-134">For more information, see [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span></span>  
  
4.  <span data-ttu-id="9bc9a-135">Asociar el certificado al usuario creado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-135">Associate the certificate with the user created in step 2.</span></span>  
  
     <span data-ttu-id="9bc9a-136">En el siguiente ejemplo se asocia el certificado de HOST_B al usuario de HOST_A.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-136">The following example, associates the certificate of HOST_B with its user on HOST_A.</span></span>  
  
    ```sql  
    USE master;  
    CREATE CERTIFICATE HOST_B_cert  
       AUTHORIZATION HOST_B_user  
       FROM FILE = 'C:\HOST_B_cert.cer'  
    GO  
    ```  
  
     <span data-ttu-id="9bc9a-137">Para obtener más información, vea [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9bc9a-137">For more information, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="9bc9a-138">Para ver los certificados de esta instancia del servidor, utilice la siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9bc9a-138">To view the certificates on this server instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.certificates;  
    ```  
  
     <span data-ttu-id="9bc9a-139">Para obtener más información, vea [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9bc9a-139">For more information, see [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span></span>  
  
5.  <span data-ttu-id="9bc9a-140">Conceda el permiso CONNECT para el inicio de sesión al extremo de creación de reflejo remoto.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-140">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
     <span data-ttu-id="9bc9a-141">Por ejemplo, para conceder permiso para HOST_A a la instancia del servidor remoto de HOST_B para que se conecte a su inicio de sesión local (es decir, para que se conecte a `HOST_B_login`), use las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] siguientes:</span><span class="sxs-lookup"><span data-stu-id="9bc9a-141">For example, to grant permission on HOST_A to the remote server instance on HOST_B to connect to its local login-that is, to connect to `HOST_B_login`-use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```sql  
    USE master;  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_B_login];  
    GO  
    ```  
  
     <span data-ttu-id="9bc9a-142">Para obtener más información, vea [GRANT &#40;permisos de punto de conexión de Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9bc9a-142">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
 <span data-ttu-id="9bc9a-143">Este último paso completa el proceso de configuración de la autenticación del certificado para que HOST_B pueda iniciar sesión en HOST_A.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-143">This completes setting up certificate authentication for HOST_B to log in to HOST_A.</span></span>  
  
 <span data-ttu-id="9bc9a-144">Ahora tiene que seguir los pasos de salida de entrada equivalentes para HOST_A en HOST_B.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-144">You now need to perform the equivalent inbound steps for HOST_A on HOST_B.</span></span> <span data-ttu-id="9bc9a-145">Estos pasos se muestran en la parte entrante del ejemplo en la sección Ejemplo a continuación.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-145">These steps are illustrated in the inbound portion of the example in the Example section, below.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bc9a-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9bc9a-146">Example</span></span>  
 <span data-ttu-id="9bc9a-147">En el siguiente ejemplo se muestra la forma de configurar HOST_B para las conexiones entrantes.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-147">The following example demonstrates configuring HOST_B for inbound connections.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9bc9a-148">Este ejemplo usa un archivo de certificado que contiene el certificado HOST_A que se ha creado por un fragmento de código en [Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones salientes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="9bc9a-148">This example uses a certificate file containing the HOST_A certificate that is created by a code snippet in [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
```sql  
USE master;  
--On HOST_B, create a login for HOST_A.  
CREATE LOGIN HOST_A_login WITH PASSWORD = 'AStrongPassword!@#';  
GO  
--Create a user, HOST_A_user, for that login.  
CREATE USER HOST_A_user FOR LOGIN HOST_A_login;  
GO  
--Obtain HOST_A certificate. (See the note   
--   preceding this example.)  
--Asscociate this certificate with the user, HOST_A_user.  
CREATE CERTIFICATE HOST_A_cert  
   AUTHORIZATION HOST_A_user  
   FROM FILE = 'C:\HOST_A_cert.cer';  
GO  
--Grant CONNECT permission for the server instance on HOST_A.  
GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO HOST_A_login;  
GO  
```  
  
 <span data-ttu-id="9bc9a-149">Si tiene planeado que la ejecución se realice en modo de seguridad alta con conmutación automática por error, debe repetir los mismos pasos de configuración para configurar el testigo de las conexiones entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-149">If you intend to run in high-safety mode with automatic failover, you must repeat the same set up steps to configure the witness for outbound and inbound connections.</span></span>  
  
 <span data-ttu-id="9bc9a-150">Para obtener información sobre la creación de una base de datos reflejada, incluido un ejemplo de Transact-SQL, vea [Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9bc9a-150">For information on creating a mirror database, including a Transact-SQL example, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="9bc9a-151">Para obtener un ejemplo de Transact-SQL sobre cómo establecer una sesión en modo de alto rendimiento, vea [Ejemplo: configurar la creación de reflejo de la base de datos mediante certificados &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9bc9a-151">For a Transact-SQL example of establishing a high-performance mode session, see [Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9bc9a-152">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9bc9a-152">.NET Framework Security</span></span>  
 <span data-ttu-id="9bc9a-153">Cuando copie un certificado en otro sistema, utilice un método de copia seguro.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-153">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="9bc9a-154">Tenga mucho cuidado de mantener todos sus certificados protegidos.</span><span class="sxs-lookup"><span data-stu-id="9bc9a-154">Be extremely careful to keep all of your certificates secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bc9a-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9bc9a-155">See Also</span></span>  
 <span data-ttu-id="9bc9a-156">[Seguridad de transporte para la creación de reflejo de la base de datos y Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="9bc9a-156">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="9bc9a-157">[GRANT &#40;permisos de punto de conexión de Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9bc9a-157">[GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span></span>  
 <span data-ttu-id="9bc9a-158">[Configurar una base de datos reflejada cifrada](set-up-an-encrypted-mirror-database.md) </span><span class="sxs-lookup"><span data-stu-id="9bc9a-158">[Set Up an Encrypted Mirror Database](set-up-an-encrypted-mirror-database.md) </span></span>  
 <span data-ttu-id="9bc9a-159">[El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9bc9a-159">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 [<span data-ttu-id="9bc9a-160">Solucionar problemas de configuración de creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9bc9a-160">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
