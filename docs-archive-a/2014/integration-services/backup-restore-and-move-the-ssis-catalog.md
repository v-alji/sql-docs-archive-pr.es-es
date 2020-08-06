---
title: Copia de seguridad, restauración y traslado del catálogo de SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: bf806aef-8556-48ab-aed5-e95de9a2204e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9de552ddd54168f516f42d9988302561616fd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671656"
---
# <a name="backup-restore-and-move-the-ssis-catalog"></a><span data-ttu-id="2c8f9-102">Copia de seguridad, restauración y traslado del catálogo de SSIS</span><span class="sxs-lookup"><span data-stu-id="2c8f9-102">Backup, Restore, and Move the SSIS Catalog</span></span>
  [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] <span data-ttu-id="2c8f9-103">incluye la base de datos de SSISDB.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-103">includes the SSISDB database.</span></span> <span data-ttu-id="2c8f9-104">En la base de datos de SSISDB, se consultan vistas para inspeccionar objetos, valores y los datos operativos que se almacenan en el catálogo de **SSISDB** , consultando las vistas de la base de datos de SSISDB.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-104">You query views in the SSISDB database to inspect objects, settings, and operational data that are stored in the **SSISDB** catalog.</span></span> <span data-ttu-id="2c8f9-105">Este tema proporciona instrucciones para hacer una copia de seguridad de la base de datos y restaurarla.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-105">This topic provides instructions for backing up and restoring the database.</span></span>  
  
 <span data-ttu-id="2c8f9-106">El catálogo de **SSISDB** almacena los paquetes que se han implementado en el servidor de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c8f9-106">The **SSISDB** catalog stores the packages that you've deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="2c8f9-107">Para más información sobre el catálogo, vea [Catálogo de SSIS](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="2c8f9-107">For more information about the catalog, see [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
##  <a name="to-back-up-the-ssis-database"></a><a name="backup"></a> <span data-ttu-id="2c8f9-108">Para realizar una copia de seguridad de la base de datos de SSIS</span><span class="sxs-lookup"><span data-stu-id="2c8f9-108">To Back up the SSIS Database</span></span>  
  
1.  <span data-ttu-id="2c8f9-109">Abra [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] y conéctese a una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c8f9-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="2c8f9-110">Para realizar una copia de seguridad de la clave maestra de la base de datos de SSISDB, use la instrucción Transact-SQL BACKUP MASTER KEY.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-110">Back up the master key for the SSISDB database, by using the BACKUP MASTER KEY Transact-SQL statement.</span></span> <span data-ttu-id="2c8f9-111">La clave se almacena en un archivo que especifique.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-111">The key is stored in a file that you specify.</span></span> <span data-ttu-id="2c8f9-112">Use una contraseña utilizada para cifrar la clave maestra del archivo.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-112">Use a password to encrypt the master key in the file.</span></span>  
  
     <span data-ttu-id="2c8f9-113">Para más información sobre la instrucción, vea [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c8f9-113">For more information about the statement, see [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
     <span data-ttu-id="2c8f9-114">En el ejemplo siguiente, la clave maestra se exporta al archivo `c:\temp directory\RCTestInstKey` .</span><span class="sxs-lookup"><span data-stu-id="2c8f9-114">In the following example, the master key is exported to the `c:\temp directory\RCTestInstKey` file.</span></span> <span data-ttu-id="2c8f9-115">La contraseña de `LS2Setup!` se usa para cifrar la clave maestra.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-115">The `LS2Setup!` password is used to encrypt the master key.</span></span>  
  
    ```  
    backup master key to file = 'c:\temp\RCTestInstKey'  
           encryption by password = 'LS2Setup!'  
  
    ```  
  
3.  <span data-ttu-id="2c8f9-116">Use el cuadro de diálogo **Copia de seguridad de la base de datos** en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]para realizar una copia de seguridad de la base de datos de SSISDB.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-116">Back up the SSISDB database by using the **Backup Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2c8f9-117">Para más información, vea: [Cómo: Realizar una copia de seguridad de una base de datos (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=231812).</span><span class="sxs-lookup"><span data-stu-id="2c8f9-117">For more information, see [How to: Back Up a Database (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=231812).</span></span>  
  
4.  <span data-ttu-id="2c8f9-118">Realice el procedimiento siguiente para generar el script CREATE LOGIN para ##MS_SSISServerCleanupJobLogin##.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-118">Generate the CREATE LOGIN script for ##MS_SSISServerCleanupJobLogin##, by doing the following.</span></span> <span data-ttu-id="2c8f9-119">Para obtener más información, vea [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c8f9-119">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
    1.  <span data-ttu-id="2c8f9-120">En el Explorador de objetos de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expanda el nodo **Seguridad** y el nodo **Inicios de sesión** .</span><span class="sxs-lookup"><span data-stu-id="2c8f9-120">In Object Explorer in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Security** node and then expand the **Logins** node.</span></span>  
  
    2.  <span data-ttu-id="2c8f9-121">Haga clic con el botón derecho en **##MS_SSISServerCleanupJobLogin##** y, después, haga clic en **Incluir inicio de sesión como** > **CREATE To** > **Nueva ventana del Editor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-121">Right-click **##MS_SSISServerCleanupJobLogin##**, and then click **Script Login as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
5.  <span data-ttu-id="2c8f9-122">Si restaura la base de datos de SSISDB a una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en la que nunca se ha creado el catálogo de SSISDB, genere el script CREATE PROCEDURE para sp_ssis_startup como se indica aquí.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-122">If you will be restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, generate the CREATE PROCEDURE script for sp_ssis_startup, by doing the following.</span></span> <span data-ttu-id="2c8f9-123">Para obtener más información, vea [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c8f9-123">For more information, see [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span>  
  
    1.  <span data-ttu-id="2c8f9-124">En explorador de objetos, expanda el nodo **bases de datos** y, a continuación, expanda el nodo **bases de datos del sistema**y  >  **master**  >  **Programmability**  >  **procedimientos almacenados** de programación maestra.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-124">In Object Explorer, expand the **Databases** node and then expand the **System Databases** > **master** > **Programmability** > **Stored Procedures** node.</span></span>  
  
    2.  <span data-ttu-id="2c8f9-125">Haga clic con el botón derecho en **dbo.sp_ssis_startup**y, después, haga clic en **Incluir procedimiento almacenado como** > **CREATE To** > **Nueva ventana del Editor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-125">Right click **dbo.sp_ssis_startup**, and then click **Script Stored Procedure as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
6.  <span data-ttu-id="2c8f9-126">Confirme que se ha iniciado el Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c8f9-126">Confirm that SQL Server Agent has been started</span></span>  
  
7.  <span data-ttu-id="2c8f9-127">Si restaura la base de datos de SSISDB a una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] donde el catálogo de SSISDB nunca se creó, genere un script para el trabajo de mantenimiento de SSIS Server. como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-127">If you will be restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, generate a script for the SSIS Server Maintenance Job by doing the following.</span></span> <span data-ttu-id="2c8f9-128">El script se crea en el Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] automáticamente cuando se crea el catálogo de SSISDB.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-128">The script is created in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent automatically when the SSISDB catalog is created.</span></span> <span data-ttu-id="2c8f9-129">El trabajo sirve de ayuda para limpiar los registros de operación de la limpieza fuera de la ventana de retención y para eliminar versiones anteriores de proyectos.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-129">The job helps clean up cleanup operation logs outside the retention window and remove older versions of projects.</span></span>  
  
    1.  <span data-ttu-id="2c8f9-130">En el Explorador de objetos, expanda el nodo **Agente SQL Server** y luego expanda el nodo **Trabajos** .</span><span class="sxs-lookup"><span data-stu-id="2c8f9-130">In Object Explorer, expand the **SQL Server Agent** node and then expand the **Jobs** node.</span></span>  
  
    2.  <span data-ttu-id="2c8f9-131">Haga clic con el botón secundario en trabajo de mantenimiento del servidor SSIS y, a continuación, haga clic en **incluir trabajo como**  >  **crear en**  >  **nueva ventana del editor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-131">Right click SSIS Server Maintenance Job, and then click **Script Job as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
### <a name="to-restore-the-ssis-database"></a><span data-ttu-id="2c8f9-132">Para restaurar la base de datos de SSIS</span><span class="sxs-lookup"><span data-stu-id="2c8f9-132">To Restore the SSIS Database</span></span>  
  
1.  <span data-ttu-id="2c8f9-133">Si va a restaurar la base de datos de SSISDB en una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en la que el catálogo de SSISDB nunca se creó, habilite Common Language Runtime (CLR) ejecutando el procedimiento almacenado sp_configure.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-133">If you are restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, enable common language runtime (clr) by running the sp_configure stored procedure.</span></span> <span data-ttu-id="2c8f9-134">Para más información, vea [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) y [clr enabled (opción)](https://go.microsoft.com/fwlink/?LinkId=231855).</span><span class="sxs-lookup"><span data-stu-id="2c8f9-134">For more information, see [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) and [clr enabled Option](https://go.microsoft.com/fwlink/?LinkId=231855).</span></span>  
  
    ```  
    use master   
           sp_configure 'clr enabled', 1  
           reconfigure  
  
    ```  
  
2.  <span data-ttu-id="2c8f9-135">Si va a restaurar la base de datos de SSISDB a una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en la que el catálogo de SSISDB nunca se creó, cree la clave asimétrica y el inicio de sesión de la clave asimétrica y conceda el permiso UNSAFE al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-135">If you are restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, create the asymmetric key and the login from the asymmetric key, and grant UNSAFE permission to the login.</span></span>  
  
    ```  
    Create Asymmetric key MS_SQLEnableSystemAssemblyLoadingKey  
           FROM Executable File = 'C:\Program Files\Microsoft SQL Server\110\DTS\Binn\Microsoft.SqlServer.IntegrationServices.Server.dll'  
  
    ```  
  
     [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="2c8f9-136">requieren permisos UNSAFE para el inicio de sesión porque este debe disponer de acceso adicional con el fin de restringir recursos como, por ejemplo la API Win32 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-136">CLR stored procedures require UNSAFE permissions to be granted to the login because the login requires additional access to restricted resources, such as the Microsoft Win32 API.</span></span> <span data-ttu-id="2c8f9-137">Para obtener más información sobre el permiso de código UNSAFE, vea [Creating an Assembly](../relational-databases/clr-integration/assemblies/creating-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="2c8f9-137">For more information about the UNSAFE code permission, see [Creating an Assembly](../relational-databases/clr-integration/assemblies/creating-an-assembly.md).</span></span>  
  
    ```  
    Create Login MS_SQLEnableSystemAssemblyLoadingUser  
           FROM Asymmetric key MS_SQLEnableSystemAssemblyLoadingKey   
  
           Grant unsafe Assembly to MS_SQLEnableSystemAssemblyLoadingUser  
  
    ```  
  
3.  <span data-ttu-id="2c8f9-138">Use el cuadro de diálogo **Restaurar base de datos** en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]para restaurar la base de datos de SSISDB a partir de una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-138">Restore the SSISDB database from the backup by using the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2c8f9-139">Para obtener más información, vea los siguientes temas.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-139">For more information, see the following topics.</span></span>  
  
    -   [<span data-ttu-id="2c8f9-140">Restaurar la base de datos &#40;página General&#41;</span><span class="sxs-lookup"><span data-stu-id="2c8f9-140">Restore Database &#40;General Page&#41;</span></span>](general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="2c8f9-141">Restaurar base de datos &#40;página Archivos&#41;</span><span class="sxs-lookup"><span data-stu-id="2c8f9-141">Restore Database &#40;Files Page&#41;</span></span>](../relational-databases/backup-restore/restore-database-files-page.md)  
  
    -   [<span data-ttu-id="2c8f9-142">Restaurar base de datos &#40;página Opciones&#41;</span><span class="sxs-lookup"><span data-stu-id="2c8f9-142">Restore Database &#40;Options Page&#41;</span></span>](../relational-databases/backup-restore/restore-database-options-page.md)  
  
4.  <span data-ttu-id="2c8f9-143">Ejecute los scripts que ha creado en [Para realizar una copia de seguridad de la base de datos de SSIS](#backup) para ##MS_SSISServerCleanupJobLogin##, sp_ssis_startup y el trabajo de mantenimiento del servidor de SSIS.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-143">Execute the scripts that you created in the [To Back up the SSIS Database](#backup) for ##MS_SSISServerCleanupJobLogin##, sp_ssis_startup, and SSIS Server Maintenance Job.</span></span> <span data-ttu-id="2c8f9-144">Confirme que se ha iniciado el Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-144">Confirm that SQL Server Agent has been started.</span></span>  
  
5.  <span data-ttu-id="2c8f9-145">Ejecute la instrucción siguiente con el fin de establecer el procedimiento de sp_ssis_startup para que se ejecute automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-145">Run the following statement to set the sp_ssis_startup prodecure for autoexecution.</span></span> <span data-ttu-id="2c8f9-146">Para más información, vea [sp_procoption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c8f9-146">For more information, see [sp_procoption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql).</span></span>  
  
    ```  
    EXEC sp_procoption N'sp_ssis_startup','startup','on'  
    ```  
  
6.  <span data-ttu-id="2c8f9-147">Asigne el usuario de SSISDB ##MS_SSISServerCleanupJobUser## (base de datos de SSISDB) a ##MS_SSISServerCleanupJobLogin## (para hacerlo, use el cuadro de diálogo **Propiedades de inicio de sesión** en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="2c8f9-147">Map the SSISDB user ##MS_SSISServerCleanupJobUser## (SSISDB database) to ##MS_SSISServerCleanupJobLogin##, by using the **Login Properties** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
7.  <span data-ttu-id="2c8f9-148">Restaure la clave maestra mediante uno de los métodos siguientes.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-148">Restore the master key by using one of the following methods.</span></span> <span data-ttu-id="2c8f9-149">Para obtener más información acerca del cifrado, vea [Encryption Hierarchy](../relational-databases/security/encryption/encryption-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="2c8f9-149">For more information about encryption, see [Encryption Hierarchy](../relational-databases/security/encryption/encryption-hierarchy.md).</span></span>  
  
    -   <span data-ttu-id="2c8f9-150">**Método 1**</span><span class="sxs-lookup"><span data-stu-id="2c8f9-150">**Method 1**</span></span>  
  
         <span data-ttu-id="2c8f9-151">Use este método si ya ha realizado una copia de seguridad de la clave maestra de la base de datos y dispone de la contraseña que se utilizó para cifrar la clave maestra.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-151">Use this method if you've already performed a backup of the database master key, and you have the password used to encrypt the master key.</span></span>  
  
        ```  
               Restore master key from file = 'c:\temp\RCTestInstKey'  
               Decryption by password = 'LS2Setup!' -- 'Password used to encrypt the master key during SSISDB backup'  
               Encryption by password = 'LS3Setup!' -- 'New Password'  
               Force  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="2c8f9-152">Confirme que la cuenta de servicio de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tiene permisos para leer el archivo de la clave de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-152">Confirm that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service account has permissions to read the backup key file.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2c8f9-153">Aparecerá el mensaje de advertencia siguiente que se muestra en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] si la clave maestra de la base de datos no se ha cifrado aún con la clave maestra de servicio.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-153">You will see the following warning message displayed in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] if the database master key has not yet been encrypted by the service master key.</span></span> <span data-ttu-id="2c8f9-154">Omita el mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-154">Ignore the warning message.</span></span>  
        >   
        >  <span data-ttu-id="2c8f9-155">**No se puede descifrar la clave maestra actual. Se omitió el error porque se especificó la opción FORCE.**</span><span class="sxs-lookup"><span data-stu-id="2c8f9-155">**The current master key cannot be decrypted. The error was ignored because the FORCE option was specified.**</span></span>  
        >   
        >  <span data-ttu-id="2c8f9-156">El argumento FORCE especifica que el proceso de restauración debe continuar aunque la clave maestra de la base de datos actual no está abierta.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-156">The FORCE argument specifies that the restore process should continue even if the current database master key is not open.</span></span> <span data-ttu-id="2c8f9-157">Dado que la clave maestra de la base de datos no se ha abierto aún en la instancia donde se están restaurando la base de datos, aparecerá este mensaje para el catálogo de SSISDB.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-157">For the SSISDB catalog, because the database master key has not been opened on the instance where you are restoring the database, you will see this message.</span></span>  
  
    -   <span data-ttu-id="2c8f9-158">**Método 2**</span><span class="sxs-lookup"><span data-stu-id="2c8f9-158">**Method 2**</span></span>  
  
         <span data-ttu-id="2c8f9-159">Use este método si tiene la contraseña original que se usó para crear SSISDB.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-159">Use this method if you have the original password that was used to create SSISDB.</span></span>  
  
        ```  
        open master key decryption by password = 'LS1Setup!' --'Password used when creating SSISDB'  
               Alter Master Key Add encryption by Service Master Key  
        ```  
  
8.  <span data-ttu-id="2c8f9-160">Determine si el esquema del catálogo de SSISDB y los binarios de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] (ensamblado de ISServerExec y SQLCLR) son compatibles (para hacerlo, ejecute [catalog.check_schema_version](/sql/integration-services/system-stored-procedures/catalog-check-schema-version)).</span><span class="sxs-lookup"><span data-stu-id="2c8f9-160">Determine whether the SSISDB catalog schema and the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] binaries (ISServerExec and SQLCLR assembly) are compatible, by running [catalog.check_schema_version](/sql/integration-services/system-stored-procedures/catalog-check-schema-version).</span></span>  
  
9. <span data-ttu-id="2c8f9-161">Para confirmar que la base de datos de SSISDB se ha restaurado correctamente, realice operaciones sobre el catálogo de SSISDB como, por ejemplo, ejecutar paquetes que se hayan implementado en el servidor de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c8f9-161">To confirm that the SSISDB database has been restored successfully, perform operations against the SSISDB catalog such as running packages that have been deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="2c8f9-162">Para más información, vea [Ejecutar un paquete en el Servidor SSIS con SQL Server Management Studio](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="2c8f9-162">For more information, see [Run a Package on the SSIS Server Using SQL Server Management Studio](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md).</span></span>  
  
### <a name="to-move-the-ssis-database"></a><span data-ttu-id="2c8f9-163">Para mover la base de datos de SSIS</span><span class="sxs-lookup"><span data-stu-id="2c8f9-163">To Move the SSIS Database</span></span>  
  
-   <span data-ttu-id="2c8f9-164">Siga las instrucciones para mover las bases de datos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-164">Follow the instructions for moving user databases.</span></span> <span data-ttu-id="2c8f9-165">Para más información, consulte [Move User Databases](../relational-databases/databases/move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="2c8f9-165">For more information, see [Move User Databases](../relational-databases/databases/move-user-databases.md).</span></span>  
  
     <span data-ttu-id="2c8f9-166">Asegúrese de realizar una copia de seguridad de la clave maestra de la base de datos de SSISDB y de proteger el archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-166">Ensure that you back up the master key for the SSISDB database and protect the backup file.</span></span> <span data-ttu-id="2c8f9-167">Para más información, vea [Para realizar una copia de seguridad de la base de datos de SSIS](#backup).</span><span class="sxs-lookup"><span data-stu-id="2c8f9-167">For more information, see [To Back up the SSIS Database](#backup).</span></span>  
  
     <span data-ttu-id="2c8f9-168">Asegúrese de que los objetos correspondientes de Integration Services (SSIS) se han creado en la nueva instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] donde aún no se haya creado el catálogo de SSISDB.</span><span class="sxs-lookup"><span data-stu-id="2c8f9-168">Ensure that the Integration Services (SSIS) relevant objects are created in the new [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog has not yet been created.</span></span>  
  
  
