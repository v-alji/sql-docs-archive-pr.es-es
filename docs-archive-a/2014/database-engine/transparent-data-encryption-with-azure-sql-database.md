---
title: Cifrado de datos transparente con Azure SQL Database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- TDE, SQL Database
- Transparent Data Encryption, SQL Database
- encryption (SQL Database) TDE
ms.assetid: 0bf7e8ff-1416-4923-9c4c-49341e208c62
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6af7c52741b85a2733b93c2b1ed8c03a14dd6343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673235"
---
# <a name="transparent-data-encryption-with-azure-sql-database"></a><span data-ttu-id="25af7-102">Cifrado de datos transparente con Base de datos SQL de Azure</span><span class="sxs-lookup"><span data-stu-id="25af7-102">Transparent Data Encryption with Azure SQL Database</span></span>
  [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] <span data-ttu-id="25af7-103">cifrado de datos transparente (vista previa) le ayuda a protegerse contra la amenaza de la actividad malintencionada realizando un cifrado y descifrado en tiempo real, copias de seguridad asociadas y archivos de registro de transacciones en reposo sin requerir cambios en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="25af7-103">transparent data encryption (preview) helps protect against the threat of malicious activity by performing real-time encryption and decryption of the database, associated backups, and transaction log files at rest without requiring changes to the application.</span></span>

 <span data-ttu-id="25af7-104">TDE cifra el almacenamiento de una base de datos completa mediante el uso de una clave simétrica denominada clave de cifrado de base de datos.</span><span class="sxs-lookup"><span data-stu-id="25af7-104">TDE encrypts the storage of an entire database by using a symmetric key called the database encryption key.</span></span> <span data-ttu-id="25af7-105">En [!INCLUDE[ssSDS](../includes/sssds-md.md)] la clave de cifrado de base de datos está protegida por un certificado de servidor integrado.</span><span class="sxs-lookup"><span data-stu-id="25af7-105">In [!INCLUDE[ssSDS](../includes/sssds-md.md)] the database encryption key is protected by a built-in server certificate.</span></span> <span data-ttu-id="25af7-106">El certificado de servidor integrado es único para cada servidor de [!INCLUDE[ssSDS](../includes/sssds-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25af7-106">The built-in server certificate is unique for each [!INCLUDE[ssSDS](../includes/sssds-md.md)] server.</span></span> <span data-ttu-id="25af7-107">Si una base de datos está en una relación de GeoDR, está protegido por una clave diferente en cada servidor.</span><span class="sxs-lookup"><span data-stu-id="25af7-107">If a database is in a GeoDR relationship, it is protected by a different key on each server.</span></span> <span data-ttu-id="25af7-108">Si hay 2 bases de datos conectadas al mismo servidor, comparten el mismo certificado integrado.</span><span class="sxs-lookup"><span data-stu-id="25af7-108">If 2 databases are connected to the same server, they share the same built-in certificate.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="25af7-109">gira automáticamente estos certificados al menos cada 90 días.</span><span class="sxs-lookup"><span data-stu-id="25af7-109">automatically rotates these certificates at least every 90 days.</span></span> <span data-ttu-id="25af7-110">Para obtener una descripción general de TDE, vea [Cifrado de datos transparente &#40;TDE&#41;](../relational-databases/security/encryption/transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="25af7-110">For a general description of TDE, see [Transparent Data Encryption &#40;TDE&#41;](../relational-databases/security/encryption/transparent-data-encryption.md).</span></span>

 [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] <span data-ttu-id="25af7-111">no admite la integración del Almacén de claves de Azure con TDE.</span><span class="sxs-lookup"><span data-stu-id="25af7-111">does not support Azure Key Vault integration with TDE.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="25af7-112">que se ejecuta en una máquina virtual de Azure puede usar una clave asimétrica del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="25af7-112">running on an Azure virtual machine can use an asymmetric key from the Key Vault.</span></span> <span data-ttu-id="25af7-113">Para obtener más información, vea [Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault](../relational-databases/security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md#ExampleA).</span><span class="sxs-lookup"><span data-stu-id="25af7-113">For more information, see [Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault](../relational-databases/security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md#ExampleA).</span></span>

||
|-|
|<span data-ttu-id="25af7-114">**Se aplica a**: [!INCLUDE[sqldbesa](../includes/sqldbesa-md.md)] ([vista previa en algunas regiones](https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span><span class="sxs-lookup"><span data-stu-id="25af7-114">**Applies to**: [!INCLUDE[sqldbesa](../includes/sqldbesa-md.md)] ([Preview in some regions](https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span></span>|

> [!IMPORTANT]
>  <span data-ttu-id="25af7-115">Actualmente, se trata de una característica de vista previa.</span><span class="sxs-lookup"><span data-stu-id="25af7-115">This is currently a preview feature.</span></span> <span data-ttu-id="25af7-116">Reconoce y acepta que la implementación del cifrado de datos transparente de [!INCLUDE[ssSDS](../includes/sssds-md.md)] en mis bases de datos está sujeta a los términos de vista previa del contrato de licencia (por ejemplo, el contrato Enterprise, contrato de Microsoft Azure o el contrato Microsoft Online Subscription), así como cualquier [término complementario de vista previa de Microsoft Azure](https://azure.microsoft.com/support/legal/preview-supplemental-terms/)aplicable.</span><span class="sxs-lookup"><span data-stu-id="25af7-116">I acknowledge and agree that implementation of [!INCLUDE[ssSDS](../includes/sssds-md.md)] transparent data encryption in my database(s) is subject to the preview terms in my license agreement (e.g. the Enterprise Agreement, Microsoft Azure Agreement, or Microsoft Online Subscription Agreement), as well as any applicable [Supplemental Terms of Use for Microsoft Azure Preview](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).</span></span>

 <span data-ttu-id="25af7-117">La vista previa del estado de TDE se aplica incluso en el subconjunto de las regiones geográficas donde la familia de la versión V12 de [!INCLUDE[ssSDS](../includes/sssds-md.md)] se anuncia como con estado de disponibilidad general.</span><span class="sxs-lookup"><span data-stu-id="25af7-117">The preview of status of TDE applies even in the subset of geographic regions where version family V12 of [!INCLUDE[ssSDS](../includes/sssds-md.md)] is announced as now being in general availability status.</span></span> <span data-ttu-id="25af7-118">TDE para [!INCLUDE[ssSDS](../includes/sssds-md.md)] no está diseñado para su uso en bases de datos de producción hasta que [!INCLUDE[msCoName](../includes/msconame-md.md)] anuncie que TDE se promueve de vista previa a disponibilidad general.</span><span class="sxs-lookup"><span data-stu-id="25af7-118">TDE for [!INCLUDE[ssSDS](../includes/sssds-md.md)] is not intended for use in production databases until [!INCLUDE[msCoName](../includes/msconame-md.md)] announces that TDE is promoted from preview to GA.</span></span> <span data-ttu-id="25af7-119">Para más información sobre [!INCLUDE[ssSDS](../includes/sssds-md.md)] V12, consulte [Novedades de Azure SQL Database](https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/).</span><span class="sxs-lookup"><span data-stu-id="25af7-119">For more information about [!INCLUDE[ssSDS](../includes/sssds-md.md)] V12, see [What's new in Azure SQL Database](https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/).</span></span>

##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="25af7-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="25af7-120">Permissions</span></span>
 <span data-ttu-id="25af7-121">Para inscriburse para obtener la vista previa y configurar TDE a través del portal de Azure, mediante la API de REST o mediante PowerShell, debe estar conectado como propietario de Azure, colaborador o administrador de seguridad de SQL.</span><span class="sxs-lookup"><span data-stu-id="25af7-121">To sign up for the preview and to configure TDE through the Azure portal, by using the REST API, or by using PowerShell, you must be connected as the Azure Owner, Contributor, or SQL Security Manager.</span></span>

 <span data-ttu-id="25af7-122">Para configurar TDE mediante [!INCLUDE[tsql](../includes/tsql-md.md)] se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25af7-122">To configure TDE by using [!INCLUDE[tsql](../includes/tsql-md.md)] requires the following:</span></span>

-   <span data-ttu-id="25af7-123">Debe estar ya registrado para la vista previa de TDE.</span><span class="sxs-lookup"><span data-stu-id="25af7-123">You must be already signed up for the TDE preview.</span></span>

-   <span data-ttu-id="25af7-124">Para crear la clave de cifrado de la base de datos debe ser un administrador de [!INCLUDE[ssSDS](../includes/sssds-md.md)] o debe ser miembro del rol **dbmanager** en la base de datos maestra y tener el permiso **CONTROL** en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="25af7-124">To create the database encryption key you must be a [!INCLUDE[ssSDS](../includes/sssds-md.md)] administrator or you must be a member of the **dbmanager** role in the master database and have the **CONTROL** permission on the database.</span></span>

-   <span data-ttu-id="25af7-125">Para ejecutar la instrucción ALTER DATABASE con la opción SET solo se requiere la pertenencia al rol **dbmanager** .</span><span class="sxs-lookup"><span data-stu-id="25af7-125">To execute the ALTER DATABASE statement with the SET option only requires membership in the **dbmanager** role.</span></span>

##  <a name="sign-up-for-the-preview-of-tde-and-enable-tde-on-a-database"></a><a name="Preview"></a><span data-ttu-id="25af7-126">Suscríbase a la versión preliminar de TDE y habilite TDE en una base de datos</span><span class="sxs-lookup"><span data-stu-id="25af7-126">Sign Up for the Preview of TDE and Enable TDE on a Database</span></span>

1.  <span data-ttu-id="25af7-127">Visite Azure portal en [https://portal.azure.com](https://portal.azure.com) e inicie sesión con su cuenta de administrador o colaborador de Azure.</span><span class="sxs-lookup"><span data-stu-id="25af7-127">Visit the Azure Portal at [https://portal.azure.com](https://portal.azure.com) and sign-in with your Azure Administrator or Contributor account.</span></span>

2.  <span data-ttu-id="25af7-128">En el encabezado de la izquierda, haga clic en a **EXAMINAR** y, a continuación, haga clic en **Bases de datos SQL**.</span><span class="sxs-lookup"><span data-stu-id="25af7-128">On the left banner, click to **BROWSE**, and then click **SQL databases**.</span></span>

3.  <span data-ttu-id="25af7-129">Con **Bases de datos SQL** seleccionado en el panel izquierdo, haga clic en la base de datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="25af7-129">With **SQL databases** selected in the left pane, click your user database.</span></span>

4.  <span data-ttu-id="25af7-130">En la hoja de la base de datos, haga clic en **Toda la configuración**.</span><span class="sxs-lookup"><span data-stu-id="25af7-130">In the database blade, click **All settings**.</span></span>

5.  <span data-ttu-id="25af7-131">En la hoja **Configuración** , haga clic en la parte **Cifrado de datos transparente (vista previa)** para abrir la hoja **VISTA PREVIA de cifrado de datos transparente** .</span><span class="sxs-lookup"><span data-stu-id="25af7-131">In the **Settings** blade, click **Transparent data encryption (preview)** part to open the **Transparent data encryption PREVIEW** blade.</span></span> <span data-ttu-id="25af7-132">Si todavía no está suscrito a la versión preliminar de TDE, se deshabilitará la configuración de cifrado de datos hasta que finalice el registro.</span><span class="sxs-lookup"><span data-stu-id="25af7-132">If you have not already signed up for the TDE preview, the data encryption settings will be disabled until you complete signup.</span></span>

6.  <span data-ttu-id="25af7-133">Haga clic en **TÉRMINOS DE LA VERSIÓN PRELIMINAR**.</span><span class="sxs-lookup"><span data-stu-id="25af7-133">Click **PREVIEW TERMS**.</span></span>

7.  <span data-ttu-id="25af7-134">Lea los términos de la versión preliminar y, si está de acuerdo con los términos, active la casilla de **EncryptionPreview datos transparentes** y, a continuación, haga clic en **Aceptar** cerca de la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="25af7-134">Read the terms of the preview, and if you agree to the terms, select the **Transparent Data encryptionPreview terms** check box, and then click **OK** near the bottom of the page.</span></span> <span data-ttu-id="25af7-135">Volver a la hoja **Data encryptionPREVIEW** , donde ahora debe estar habilitado el botón de **cifrado de datos** .</span><span class="sxs-lookup"><span data-stu-id="25af7-135">Returning to the **Data encryptionPREVIEW** blade, where the **Data encryption** button should now be enabled.</span></span>

8.  <span data-ttu-id="25af7-136">En la hoja **VERSIÓN PRELIMINAR de cifrado de datos** , mueva el botón **Cifrado de datos** a la posición **Activado**, y, a continuación, haga clic en **Guardar** (en la parte superior de la página) para aplicar la configuración.</span><span class="sxs-lookup"><span data-stu-id="25af7-136">In the **Data encryption PREVIEW** blade, move the **Data encryption** button to **On**, and then click **Save** (at the top of the page) to apply the setting.</span></span> <span data-ttu-id="25af7-137">El **Estado de cifrado** aproximará el progreso del cifrado de datos transparente.</span><span class="sxs-lookup"><span data-stu-id="25af7-137">The **Encryption status** will approximate the progress of the transparent data encryption.</span></span>

     <span data-ttu-id="25af7-138">![SQLDB_TDE_TermsNewUI](../../2014/database-engine/media/sqldb-tde-termsnewui.png "SQLDB_TDE_TermsNewUI")</span><span class="sxs-lookup"><span data-stu-id="25af7-138">![SQLDB_TDE_TermsNewUI](../../2014/database-engine/media/sqldb-tde-termsnewui.png "SQLDB_TDE_TermsNewUI")</span></span>

     <span data-ttu-id="25af7-139">También puede supervisar el progreso del cifrado mediante la conexión a [!INCLUDE[ssSDS](../includes/sssds-md.md)] mediante una herramienta de consulta como [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] como un usuario de base de datos con el permiso **VER ESTADO DE LA BASE DE DATOS** .</span><span class="sxs-lookup"><span data-stu-id="25af7-139">You can also monitor the progress of encryption by connecting to [!INCLUDE[ssSDS](../includes/sssds-md.md)] using a query tool such as [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] as a database user with the **VIEW DATABASE STATE** permission.</span></span> <span data-ttu-id="25af7-140">Consulte la `encryption_state` columna de la vista [sys. dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="25af7-140">Query the `encryption_state` column of the [sys.dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) view.</span></span>

##  <a name="enabling-tde-on-sssds-by-using-transact-sql"></a><a name="Encrypt"></a><span data-ttu-id="25af7-141">Habilitar TDE en [!INCLUDE[ssSDS](../includes/sssds-md.md)] mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="25af7-141">Enabling TDE on [!INCLUDE[ssSDS](../includes/sssds-md.md)] by Using Transact-SQL</span></span>
 <span data-ttu-id="25af7-142">En los pasos siguientes se supone que ya se ha registrado para la vista previa.</span><span class="sxs-lookup"><span data-stu-id="25af7-142">The following steps, assume you have already signed up for the preview.</span></span>

###  <a name="TsqlProcedure"></a>

1.  <span data-ttu-id="25af7-143">Conéctese a la base de datos mediante un inicio de sesión de administrador o de miembro del rol **dbmanager** de la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="25af7-143">Connect to the database using a login that is an administrator or a member of the **dbmanager** role in the master database.</span></span>

2.  <span data-ttu-id="25af7-144">Ejecute las siguientes instrucciones para crear una clave de cifrado de base de datos y cifrar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="25af7-144">Execute the following statements to create a database encryption key and encrypt the database.</span></span>

    ```sql
    -- Create the database encryption key that will be used for TDE.
    CREATE DATABASE ENCRYPTION KEY 
    WITH ALGORITHM = AES_256 
    ENCRYPTION BY SERVER CERTIFICATE ##MS_TdeCertificate##;

    -- Enable encryption
    ALTER DATABASE [AdventureWorks] SET ENCRYPTION ON;
    GO
    ```

3.  <span data-ttu-id="25af7-145">Para supervisar el progreso del cifrado en [!INCLUDE[ssSDS](../includes/sssds-md.md)] , los usuarios de la base de datos con el permiso **View Database State** pueden consultar la `encryption_state` columna de la vista [Sys. dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="25af7-145">To monitor the progress of encryption on [!INCLUDE[ssSDS](../includes/sssds-md.md)], database users with the **VIEW DATABASE STATE** permission can query the `encryption_state` column of the [sys.dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) view.</span></span>

## <a name="enabling-tde-on-sql-database-by-using-powershell"></a><span data-ttu-id="25af7-146">Habilitar TDE en SQL Database mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="25af7-146">Enabling TDE on SQL Database by Using PowerShell</span></span>
 <span data-ttu-id="25af7-147">Mediante Azure PowerShell puede ejecutar el comando siguiente para activar/desactivar TDE.</span><span class="sxs-lookup"><span data-stu-id="25af7-147">Using the Azure PowerShell you can run the following command to turn TDE on/off.</span></span> <span data-ttu-id="25af7-148">Es necesario conectar su cuenta a la ventana de PS antes de ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="25af7-148">You do have to connect your account to the PS window before running the command.</span></span> <span data-ttu-id="25af7-149">En los pasos siguientes se supone que ya se ha registrado para la vista previa.</span><span class="sxs-lookup"><span data-stu-id="25af7-149">The following steps, assume you have already signed up for the preview.</span></span> <span data-ttu-id="25af7-150">Para obtener información adicional acerca de PowerShell, consulte [Cómo instalar y configurar Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span><span class="sxs-lookup"><span data-stu-id="25af7-150">For additional information about PowerShell, see [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span>

1.  <span data-ttu-id="25af7-151">Para habilitar TDE, devuelva el estado de TDE y visualice la actividad de cifrado.</span><span class="sxs-lookup"><span data-stu-id="25af7-151">To enable TDE, return the TDE status, and view the encryption activity.</span></span>

    ```powershell
    Switch-AzureMode -Name AzureResourceManager
    Set-AzureSqlDatabaseTransparentDataEncryption -ServerName "myserver" -ResourceGroupName "Default-SQL-WestUS" -DatabaseName "database1" -State "Enabled"

    Get-AzureSqlDatabaseTransparentDataEncryption -ServerName "myserver" -ResourceGroupName "Default-SQL-WestUS" -DatabaseName "database1"
    Get-AzureSqlDatabaseTransparentDataEncryptionActivity -ServerName "myserver" -ResourceGroupName "Default-SQL-WestUS" -DatabaseName "database1"
    ```

2.  <span data-ttu-id="25af7-152">Para deshabilitar TDE:</span><span class="sxs-lookup"><span data-stu-id="25af7-152">To disable TDE:</span></span>

    ```powershell
    Set-AzureSqlDatabaseTransparentDataEncryption -ServerName "myserver" -ResourceGroupName "Default-SQL-WestUS" -DatabaseName "database1" -State "Disabled"
    Switch-AzureMode -Name AzureServiceManagement
    ```

##  <a name="decrypting-a-tde-protected-database-on-sssds"></a><a name="Decrypt"></a><span data-ttu-id="25af7-153">Descifrado de una base de datos protegida por TDE en[!INCLUDE[ssSDS](../includes/sssds-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25af7-153">Decrypting a TDE Protected Database on [!INCLUDE[ssSDS](../includes/sssds-md.md)]</span></span>

#### <a name="to-disable-tde-by-using-the-azure-portal"></a><span data-ttu-id="25af7-154">Para deshabilitar TDE mediante Azure Portal</span><span class="sxs-lookup"><span data-stu-id="25af7-154">To Disable TDE by Using the Azure Portal</span></span>

1.  <span data-ttu-id="25af7-155">Visite Azure portal en [https://portal.azure.com](https://portal.azure.com) e inicie sesión con su cuenta de administrador o colaborador de Azure.</span><span class="sxs-lookup"><span data-stu-id="25af7-155">Visit the Azure Portal at [https://portal.azure.com](https://portal.azure.com) and sign-in with your Azure Administrator or Contributor account.</span></span>

2.  <span data-ttu-id="25af7-156">En el encabezado de la izquierda, haga clic en a **EXAMINAR** y, a continuación, haga clic en **Bases de datos SQL**.</span><span class="sxs-lookup"><span data-stu-id="25af7-156">On the left banner, click to **BROWSE**, and then click **SQL databases**.</span></span>

3.  <span data-ttu-id="25af7-157">Con **Bases de datos SQL** seleccionado en el panel izquierdo, haga clic en la base de datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="25af7-157">With **SQL databases** selected in the left pane, click your user database.</span></span>

4.  <span data-ttu-id="25af7-158">En la hoja de la base de datos, haga clic en **Toda la configuración**.</span><span class="sxs-lookup"><span data-stu-id="25af7-158">In the database blade, click **All settings**.</span></span>

5.  <span data-ttu-id="25af7-159">En la hoja **Configuración** , haga clic en la parte **Cifrado de datos transparente (vista previa)** para abrir la hoja **VISTA PREVIA de cifrado de datos transparente** .</span><span class="sxs-lookup"><span data-stu-id="25af7-159">In the **Settings** blade, click **Transparent data encryption (preview)** part to open the **Transparent data encryption PREVIEW** blade.</span></span>

6.  <span data-ttu-id="25af7-160">En la hoja **VERSIÓN PRELIMINAR del cifrado de datos transparente** , mueva el botón **Cifrado de datos** a la posición **Desactivado**, y, a continuación, haga clic en **Guardar** (en la parte superior de la página) para aplicar la configuración.</span><span class="sxs-lookup"><span data-stu-id="25af7-160">In the **Transparent data encryption PREVIEW** blade, move the **Data encryption** button to **Off**, and then click **Save** (at the top of the page) to apply the setting.</span></span> <span data-ttu-id="25af7-161">El **Estado de cifrado** aproximará el progreso del descifrado de datos transparente.</span><span class="sxs-lookup"><span data-stu-id="25af7-161">The **Encryption status** will approximate the progress of the transparent data decryption.</span></span>

     <span data-ttu-id="25af7-162">También puede supervisar el progreso del descifrado mediante la conexión a [!INCLUDE[ssSDS](../includes/sssds-md.md)] mediante una herramienta de consulta como [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] como un usuario de base de datos con el permiso **VER ESTADO DE LA BASE DE DATOS** .</span><span class="sxs-lookup"><span data-stu-id="25af7-162">You can also monitor the progress of decryption by connecting to [!INCLUDE[ssSDS](../includes/sssds-md.md)] using a query tool such as [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] as a database user with the **VIEW DATABASE STATE** permission.</span></span> <span data-ttu-id="25af7-163">Consulte la `encryption_state` columna de la vista [sys. dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25af7-163">Query the `encryption_state` column of the [sys.dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql)view.</span></span>

#### <a name="to-disable-tde-by-using-transact-sql"></a><span data-ttu-id="25af7-164">Para deshabilitar TDE mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="25af7-164">To Disable TDE by Using Transact-SQL</span></span>

1.  <span data-ttu-id="25af7-165">Conéctese a la base de datos mediante un inicio de sesión de administrador o de miembro del rol **dbmanager** de la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="25af7-165">Connect to the database using a login that is an administrator or a member of the **dbmanager** role in the master database.</span></span>

2.  <span data-ttu-id="25af7-166">Ejecute las siguientes instrucciones para descifrar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="25af7-166">Execute the following statements to decrypt the database.</span></span>

    ```sql
    -- Enable encryption
    ALTER DATABASE [AdventureWorks] SET ENCRYPTION OFF;
    GO
    ```

3.  <span data-ttu-id="25af7-167">Para supervisar el progreso del cifrado en [!INCLUDE[ssSDS](../includes/sssds-md.md)] , los usuarios de la base de datos con el permiso **View Database State** pueden consultar la `encryption_state` columna de la vista [Sys. dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="25af7-167">To monitor the progress of encryption on [!INCLUDE[ssSDS](../includes/sssds-md.md)], database users with the **VIEW DATABASE STATE** permission can query the `encryption_state` column of the [sys.dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) view.</span></span>

##  <a name="working-with-tde-protected-databases-on-sssds"></a><a name="Working"></a><span data-ttu-id="25af7-168">Trabajar con bases de datos protegidas por TDE en[!INCLUDE[ssSDS](../includes/sssds-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25af7-168">Working with TDE Protected Databases on [!INCLUDE[ssSDS](../includes/sssds-md.md)]</span></span>
 <span data-ttu-id="25af7-169">No es necesario descifrar las bases de datos para las operaciones dentro de Azure.</span><span class="sxs-lookup"><span data-stu-id="25af7-169">You do not need to decrypt databases for operations within Azure.</span></span> <span data-ttu-id="25af7-170">La configuración de TDE en la base de datos de origen o la base de datos principal se hereda de forma transparente en el destino.</span><span class="sxs-lookup"><span data-stu-id="25af7-170">The TDE settings on the source database or primary database are transparently inherited on the target.</span></span> <span data-ttu-id="25af7-171">Aquí se incluyen operaciones que implican:</span><span class="sxs-lookup"><span data-stu-id="25af7-171">This includes operations involving:</span></span>

-   <span data-ttu-id="25af7-172">Restauración geográfica</span><span class="sxs-lookup"><span data-stu-id="25af7-172">Geo-Restore</span></span>

-   <span data-ttu-id="25af7-173">Restauración a un momento dado de autoservicio</span><span class="sxs-lookup"><span data-stu-id="25af7-173">Self-Service Point in Time Restore</span></span>

-   <span data-ttu-id="25af7-174">Restaurar una base de datos eliminada</span><span class="sxs-lookup"><span data-stu-id="25af7-174">Restore a Deleted Database</span></span>

-   <span data-ttu-id="25af7-175">Geo_Replication activa</span><span class="sxs-lookup"><span data-stu-id="25af7-175">Active Geo_Replication</span></span>

-   <span data-ttu-id="25af7-176">Creación de la copia de una base de datos</span><span class="sxs-lookup"><span data-stu-id="25af7-176">Creating a Database Copy</span></span>

##  <a name="moving-a-tde-protected-database-on-using-bacpac-files"></a><a name="Moving"></a><span data-ttu-id="25af7-177">Mover una base de datos protegida por TDE al usar. Archivos BacPac</span><span class="sxs-lookup"><span data-stu-id="25af7-177">Moving a TDE Protected Database on using .Bacpac Files</span></span>
 <span data-ttu-id="25af7-178">Cuando se exporta una base de datos protegida con TDE mediante la función Exportar base de datos del Portal de [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] o el asistente para la importación y exportación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], el contenido de la base de datos no se cifra.</span><span class="sxs-lookup"><span data-stu-id="25af7-178">When exporting a TDE protected database using the Export Database function in the [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] Portal or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard, the content of the database is not encrypted.</span></span> <span data-ttu-id="25af7-179">El contenido se almacena en archivos .bacpac que no están cifrados.</span><span class="sxs-lookup"><span data-stu-id="25af7-179">The content is stored in .bacpac files which are not encrypted.</span></span>  <span data-ttu-id="25af7-180">Asegúrese de proteger adecuadamente los archivos .bacpac y de habilitar TDE una vez completada la importación de la nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="25af7-180">Be sure to protect the .bacpac files appropriately and enable TDE once import of the new database is completed.</span></span>

## <a name="related-sql-server-topic"></a><span data-ttu-id="25af7-181">Tema de SQL Server relacionado</span><span class="sxs-lookup"><span data-stu-id="25af7-181">Related SQL Server Topic</span></span>
 [<span data-ttu-id="25af7-182">Habilitar TDE con EKM</span><span class="sxs-lookup"><span data-stu-id="25af7-182">Enable TDE Using EKM</span></span>](../relational-databases/security/encryption/enable-tde-on-sql-server-using-ekm.md)

## <a name="see-also"></a><span data-ttu-id="25af7-183">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25af7-183">See Also</span></span>
 <span data-ttu-id="25af7-184">[Cifrado de datos transparente &#40;TDE&#41;](../relational-databases/security/encryption/transparent-data-encryption.md) [crear credencial &#40;transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [crear una clave asimétrica &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [crear una clave de cifrado de base de datos &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-encryption-key-transact-sql) [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) opciones set de la base de datos &#40;[Transact-SQL](/sql/t-sql/statements/alter-database-transact-sql-set-options)&#41;</span><span class="sxs-lookup"><span data-stu-id="25af7-184">[Transparent Data Encryption &#40;TDE&#41;](../relational-databases/security/encryption/transparent-data-encryption.md) [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-encryption-key-transact-sql) [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)</span></span>
