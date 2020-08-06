---
title: Habilitar TDE con EKM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], TDE using an EKM
- TDE, EKM how to
- EKM, TDE how to
- Transparent Data Encryption, using EKM
ms.assetid: b892e7a7-95bd-4903-bf54-55ce08e225af
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: e659c5ff0245fdb17192b845eafc60badf5e295e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750609"
---
# <a name="enable-tde-using-ekm"></a><span data-ttu-id="8babb-102">Habilitar TDE con EKM</span><span class="sxs-lookup"><span data-stu-id="8babb-102">Enable TDE Using EKM</span></span>
  <span data-ttu-id="8babb-103">En este tema se describe cómo habilitar el cifrado de datos transparente (TDE) en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] para proteger una clave de cifrado de base de datos mediante una clave asimétrica almacenada en un módulo EKM (Administración extensible de claves) con [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8babb-103">This topic describes how to enable transparent data encryption (TDE) in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] to protect a database encryption key by using an asymmetric key stored in an extensible key management (EKM) module with [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8babb-104">TDE cifra el almacenamiento de una base de datos completa mediante el uso de una clave simétrica denominada clave de cifrado de base de datos.</span><span class="sxs-lookup"><span data-stu-id="8babb-104">TDE encrypts the storage of an entire database by using a symmetric key called the database encryption key.</span></span> <span data-ttu-id="8babb-105">La clave de cifrado de base de datos también se puede proteger utilizando un certificado que se protege mediante la clave maestra de base de datos de la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="8babb-105">The database encryption key can also be protected using a certificate which is protected by the database master key of the master database.</span></span> <span data-ttu-id="8babb-106">Para obtener más información sobre cómo proteger la clave de cifrado de base de datos usando la clave maestra de base de datos, vea [Cifrado de datos transparente &#40;TDE&#41;](transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="8babb-106">For more information about protecting the database encryption key by using the database master key, see [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span></span> <span data-ttu-id="8babb-107">Para obtener más información sobre cómo configurar TDE cuando [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se está ejecutando en una máquina virtual de Azure, vea [Administración extensible de claves con el Almacén de claves de Azure &#40;SQL Server&#41;](extensible-key-management-using-azure-key-vault-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8babb-107">For information about configuring TDE when [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is running on an Azure VM, see [Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;](extensible-key-management-using-azure-key-vault-sql-server.md).</span></span>  
  
 <span data-ttu-id="8babb-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="8babb-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8babb-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="8babb-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8babb-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="8babb-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8babb-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8babb-111">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="8babb-112">Para habilitar TDE mediante EKM usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8babb-112">To enable TDE using EKM, using Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8babb-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="8babb-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8babb-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="8babb-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8babb-115">Debe ser un usuario con muchos privilegios (como un administrador del sistema) para crear una clave de cifrado de base de datos y cifrar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="8babb-115">You must be a high privileged user (such as a system administrator) to create a database encryption key and encrypt a database.</span></span> <span data-ttu-id="8babb-116">Ese usuario debe poder ser autenticado por el módulo EKM.</span><span class="sxs-lookup"><span data-stu-id="8babb-116">That user must be able to be authenticated by the EKM module.</span></span>  
  
-   <span data-ttu-id="8babb-117">Tras iniciar, el [!INCLUDE[ssDE](../../../includes/ssde-md.md)] debe abrir la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8babb-117">Upon start up the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must open the database.</span></span> <span data-ttu-id="8babb-118">Para ello, debe crear una credencial que será autenticada por EKM y agregarla a un inicio de sesión que se basa en una clave asimétrica.</span><span class="sxs-lookup"><span data-stu-id="8babb-118">To do this, you should create a credential that will be authenticated by the EKM, and add it to a login that is based on an asymmetric key.</span></span> <span data-ttu-id="8babb-119">Los usuarios no pueden iniciar sesión mediante ese inicio de sesión, pero el [!INCLUDE[ssDE](../../../includes/ssde-md.md)] podrá autenticarse con el dispositivo EKM.</span><span class="sxs-lookup"><span data-stu-id="8babb-119">Users cannot login using that login, but the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] will be able to authenticate itself with the EKM device.</span></span>  
  
-   <span data-ttu-id="8babb-120">Si la clave asimétrica almacenada en el módulo EKM se pierde, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]no podrá abrir la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8babb-120">If the asymmetric key stored in the EKM module is lost, the database will not be able to be opened by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8babb-121">Si el proveedor EKM permite hacer una copia de seguridad de la clave asimétrica, debería crear una y almacenarla en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="8babb-121">If the EKM provider lets you back up the asymmetric key, you should create a back up and store it in a secure location.</span></span>  
  
-   <span data-ttu-id="8babb-122">Las opciones y los parámetros requeridos por el proveedor de EKM pueden diferir de lo que se proporciona en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8babb-122">The options and parameters required by your EKM provider can differ from what is provided in the code example below.</span></span> <span data-ttu-id="8babb-123">Para obtener más información, consulte al proveedor de EKM.</span><span class="sxs-lookup"><span data-stu-id="8babb-123">For more information, see your EKM provider.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8babb-124">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8babb-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8babb-125">Permisos</span><span class="sxs-lookup"><span data-stu-id="8babb-125">Permissions</span></span>  
 <span data-ttu-id="8babb-126">En este tema se utilizan los permisos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8babb-126">This topic uses the following permissions:</span></span>  
  
-   <span data-ttu-id="8babb-127">Para cambiar una opción de configuración y ejecutar la instrucción RECONFIGURE, debe tener el permiso ALTER SETTINGS de nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="8babb-127">To change a configuration option and run the RECONFIGURE statement, you must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="8babb-128">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="8babb-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
-   <span data-ttu-id="8babb-129">Requiere el permiso ALTER ANY CREDENTIAL.</span><span class="sxs-lookup"><span data-stu-id="8babb-129">Requires ALTER ANY CREDENTIAL permission.</span></span>  
  
-   <span data-ttu-id="8babb-130">Requiere el permiso ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="8babb-130">Requires ALTER ANY LOGIN permission.</span></span>  
  
-   <span data-ttu-id="8babb-131">Requiere el permiso CREATE ASYMMETRIC KEY.</span><span class="sxs-lookup"><span data-stu-id="8babb-131">Requires CREATE ASYMMETRIC KEY permission.</span></span>  
  
-   <span data-ttu-id="8babb-132">Requiere el permiso CONTROL en la base de datos para cifrarla.</span><span class="sxs-lookup"><span data-stu-id="8babb-132">Requires CONTROL permission on the database to encrypt the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8babb-133">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8babb-133">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-tde-using-ekm"></a><span data-ttu-id="8babb-134">Para habilitar TDE usando EKM</span><span class="sxs-lookup"><span data-stu-id="8babb-134">To enable TDE using EKM</span></span>  
  
1.  <span data-ttu-id="8babb-135">Copie los archivos proporcionados por el proveedor EKM a una ubicación adecuada en el equipo de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8babb-135">Copy the files supplied by the EKM provider to an appropriate location on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="8babb-136">En este ejemplo, usamos la carpeta **C:\EKM** .</span><span class="sxs-lookup"><span data-stu-id="8babb-136">In this example, we use the **C:\EKM** folder.</span></span>  
  
2.  <span data-ttu-id="8babb-137">Instale los certificados en el equipo tal y como requiera el proveedor EKM.</span><span class="sxs-lookup"><span data-stu-id="8babb-137">Install certificates to the computer as required by your EKM provider.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="8babb-138">no proporciona un proveedor EKM.</span><span class="sxs-lookup"><span data-stu-id="8babb-138">does not supply an EKM provider.</span></span> <span data-ttu-id="8babb-139">Cada proveedor EKM puede tener procedimientos diferentes para instalar, configurar y autorizar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8babb-139">Each EKM provider can have different procedures for installing, configuring and authorizing users.</span></span>  <span data-ttu-id="8babb-140">Consulte la documentación del proveedor EKM para completar este paso.</span><span class="sxs-lookup"><span data-stu-id="8babb-140">Consult your EKM provider documentation to complete this step.</span></span>  
  
3.  <span data-ttu-id="8babb-141">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8babb-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
4.  <span data-ttu-id="8babb-142">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="8babb-142">On the Standard bar, click **New Query**.</span></span>  
  
5.  <span data-ttu-id="8babb-143">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="8babb-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Enable advanced options.  
    sp_configure 'show advanced options', 1 ;  
    GO  
    RECONFIGURE ;  
    GO  
    -- Enable EKM provider  
    sp_configure 'EKM provider enabled', 1 ;  
    GO  
    RECONFIGURE ;  
    GO  
    -- Create a cryptographic provider, which we have chosen to call "EKM_Prov," based on an EKM provider  
  
    CREATE CRYPTOGRAPHIC PROVIDER EKM_Prov   
    FROM FILE = 'C:\EKM_Files\KeyProvFile.dll' ;  
    GO  
  
    -- Create a credential that will be used by system administrators.  
    CREATE CREDENTIAL sa_ekm_tde_cred   
    WITH IDENTITY = 'Identity1',   
    SECRET = 'q*gtev$0u#D1v'   
    FOR CRYPTOGRAPHIC PROVIDER EKM_Prov ;  
    GO  
  
    -- Add the credential to a high privileged user such as your   
    -- own domain login in the format [DOMAIN\login].  
    ALTER LOGIN Contoso\Mary  
    ADD CREDENTIAL sa_ekm_tde_cred ;  
    GO  
    -- create an asymmetric key stored inside the EKM provider  
    USE master ;  
    GO  
    CREATE ASYMMETRIC KEY ekm_login_key   
    FROM PROVIDER [EKM_Prov]  
    WITH ALGORITHM = RSA_512,  
    PROVIDER_KEY_NAME = 'SQL_Server_Key' ;  
    GO  
  
    -- Create a credential that will be used by the Database Engine.  
    CREATE CREDENTIAL ekm_tde_cred   
    WITH IDENTITY = 'Identity2'   
    , SECRET = 'jeksi84&sLksi01@s'   
    FOR CRYPTOGRAPHIC PROVIDER EKM_Prov ;  
  
    -- Add a login used by TDE, and add the new credential to the login.  
    CREATE LOGIN EKM_Login   
    FROM ASYMMETRIC KEY ekm_login_key ;  
    GO  
    ALTER LOGIN EKM_Login   
    ADD CREDENTIAL ekm_tde_cred ;  
    GO  
  
    -- Create the database encryption key that will be used for TDE.  
    USE AdventureWorks2012 ;  
    GO  
    CREATE DATABASE ENCRYPTION KEY  
    WITH ALGORITHM  = AES_128  
    ENCRYPTION BY SERVER ASYMMETRIC KEY ekm_login_key ;  
    GO  
  
    -- Alter the database to enable transparent data encryption.  
    ALTER DATABASE AdventureWorks2012   
    SET ENCRYPTION ON ;  
    GO  
    ```  
  
 <span data-ttu-id="8babb-144">Para obtener más información, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8babb-144">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="8babb-145">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8babb-145">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
-   [<span data-ttu-id="8babb-146">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8babb-146">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-cryptographic-provider-transact-sql)  
  
-   [<span data-ttu-id="8babb-147">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8babb-147">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)  
  
-   [<span data-ttu-id="8babb-148">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8babb-148">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)  
  
-   [<span data-ttu-id="8babb-149">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8babb-149">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
-   [<span data-ttu-id="8babb-150">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8babb-150">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)  
  
-   [<span data-ttu-id="8babb-151">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8babb-151">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)  
  
-   [<span data-ttu-id="8babb-152">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8babb-152">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
-   [<span data-ttu-id="8babb-153">Administración extensible de claves con el Almacén de claves de Azure &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8babb-153">Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;</span></span>](extensible-key-management-using-azure-key-vault-sql-server.md)  
  
-   [<span data-ttu-id="8babb-154">Cifrado de datos transparente con Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="8babb-154">Transparent Data Encryption with Azure SQL Database</span></span>](../../../database-engine/transparent-data-encryption-with-azure-sql-database.md)  
  
  
