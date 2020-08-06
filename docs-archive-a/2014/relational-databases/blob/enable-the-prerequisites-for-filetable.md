---
title: Habilitar los requisitos previos de FileTables | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], prerequisites
ms.assetid: 6286468c-9dc9-4eda-9961-071d2a36ebd6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5d5d2c5dab7909ec5403911d482823f488cdd809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662111"
---
# <a name="enable-the-prerequisites-for-filetable"></a><span data-ttu-id="666e5-102">Habilitar los requisitos previos de FileTables</span><span class="sxs-lookup"><span data-stu-id="666e5-102">Enable the Prerequisites for FileTable</span></span>
  <span data-ttu-id="666e5-103">Describe cómo habilitar los requisitos previos para crear y usar FileTables.</span><span class="sxs-lookup"><span data-stu-id="666e5-103">Describes how to enable the prerequisites for creating and using FileTables.</span></span>  
  
##  <a name="enabling-the-prerequisites-for-filetable"></a><a name="EnablePrereq"></a> <span data-ttu-id="666e5-104">Habilitar los requisitos previos para FileTable</span><span class="sxs-lookup"><span data-stu-id="666e5-104">Enabling the Prerequisites for FileTable</span></span>  
 <span data-ttu-id="666e5-105">Para habilitar los requisitos previos para crear y usar FileTables, habilite los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="666e5-105">To enable the prerequisites for creating and using FileTables, enable the following items:</span></span>  
  
-   <span data-ttu-id="666e5-106">**En el nivel de instancia:**</span><span class="sxs-lookup"><span data-stu-id="666e5-106">**At the instance level:**</span></span>  
  
    -   [<span data-ttu-id="666e5-107">Habilitar FILESTREAM en el nivel de instancia</span><span class="sxs-lookup"><span data-stu-id="666e5-107">Enabling FILESTREAM at the Instance Level</span></span>](#BasicsFilestream)  
  
-   <span data-ttu-id="666e5-108">**En el nivel de base de datos:**</span><span class="sxs-lookup"><span data-stu-id="666e5-108">**At the database level:**</span></span>  
  
    -   [<span data-ttu-id="666e5-109">Proporcionar un grupo de archivos de FILESTREAM en el nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="666e5-109">Providing a FILESTREAM Filegroup at the Database Level</span></span>](#filegroup)  
  
    -   [<span data-ttu-id="666e5-110">Habilitar el acceso no transaccional en el nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="666e5-110">Enabling Non-Transactional Access at the Database Level</span></span>](#BasicsNTAccess)  
  
    -   [<span data-ttu-id="666e5-111">Especificar un directorio para FileTables en el nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="666e5-111">Specifying a Directory for FileTables at the Database Level</span></span>](#BasicsDirectory)  
  
##  <a name="enabling-filestream-at-the-instance-level"></a><a name="BasicsFilestream"></a> <span data-ttu-id="666e5-112">Habilitar FILESTREAM en el nivel de instancia</span><span class="sxs-lookup"><span data-stu-id="666e5-112">Enabling FILESTREAM at the Instance Level</span></span>  
 <span data-ttu-id="666e5-113">Las FileTables amplían las capacidades de la característica FILESTREAM de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="666e5-113">FileTables extend the capabilities of the FILESTREAM feature of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="666e5-114">Por lo tanto, debe habilitar FILESTREAM para el acceso de E/S de archivos en el nivel de Windows y en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antes de poder crear y usar FileTables.</span><span class="sxs-lookup"><span data-stu-id="666e5-114">Therefore you have to enable FILESTREAM for file I/O access at the Windows level and on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you can create and use FileTables.</span></span>  
  
###  <a name="how-to-enable-filestream-at-the-instance-level"></a><a name="HowToFilestream"></a> <span data-ttu-id="666e5-115">Procedimientos para: habilitar FILESTREAM en el nivel de instancia</span><span class="sxs-lookup"><span data-stu-id="666e5-115">How To: Enable FILESTREAM at the Instance Level</span></span>  
 <span data-ttu-id="666e5-116">Para obtener información sobre cómo habilitar FILESTREAM, vea [Habilitar y configurar FILESTREAM](enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="666e5-116">For information about how to enable FILESTREAM, see [Enable and Configure FILESTREAM](enable-and-configure-filestream.md).</span></span>  
  
 <span data-ttu-id="666e5-117">Cuando se llama a `sp_configure` para habilitar FILESTREAM en el nivel de instancia, tiene que establecer la opción filestream_access_level en 2.</span><span class="sxs-lookup"><span data-stu-id="666e5-117">When you call `sp_configure` to enable FILESTREAM at the instance level, you have to set the filestream_access_level option to 2.</span></span> <span data-ttu-id="666e5-118">Para obtener más información, vea [filestream access level (opción de configuración del servidor)](../../database-engine/configure-windows/filestream-access-level-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="666e5-118">For more information, see [filestream access level Server Configuration Option](../../database-engine/configure-windows/filestream-access-level-server-configuration-option.md).</span></span>  
  
###  <a name="how-to-allow-filestream-through-the-firewall"></a><a name="firewall"></a> <span data-ttu-id="666e5-119">Procedimientos para: permitir FILESTREAM a través del firewall</span><span class="sxs-lookup"><span data-stu-id="666e5-119">How To: Allow FILESTREAM through the Firewall</span></span>  
 <span data-ttu-id="666e5-120">Para obtener información acerca de cómo habilitar FILESTREAM a través del firewall, vea [Configure a Firewall for FILESTREAM Access](configure-a-firewall-for-filestream-access.md).</span><span class="sxs-lookup"><span data-stu-id="666e5-120">For information about how to allow FILESTREAM through the firewall, see [Configure a Firewall for FILESTREAM Access](configure-a-firewall-for-filestream-access.md).</span></span>  
  
##  <a name="providing-a-filestream-filegroup-at-the-database-level"></a><a name="filegroup"></a> <span data-ttu-id="666e5-121">Proporcionar un grupo de archivos de FILESTREAM en el nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="666e5-121">Providing a FILESTREAM Filegroup at the Database Level</span></span>  
 <span data-ttu-id="666e5-122">Para poder crear tablas FileTable en una base de datos, esta debe tener un grupo de archivos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="666e5-122">Before you can create FileTables in a database, the database must have a FILESTREAM filegroup.</span></span> <span data-ttu-id="666e5-123">Para obtener más información sobre este requisito previo, vea [Crear una base de datos habilitada para FILESTREAM](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="666e5-123">For more information about this prerequisite, see [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
##  <a name="enabling-non-transactional-access-at-the-database-level"></a><a name="BasicsNTAccess"></a> <span data-ttu-id="666e5-124">Habilitar el acceso no transaccional en el nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="666e5-124">Enabling Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="666e5-125">Las FileTables permiten que las aplicaciones Windows obtengan un identificador de archivo de Windows en los datos FILESTREAM sin que sea necesaria ninguna transacción.</span><span class="sxs-lookup"><span data-stu-id="666e5-125">FileTables let Windows applications obtain a Windows file handle to FILESTREAM data without requiring a transaction.</span></span> <span data-ttu-id="666e5-126">Para permitir este acceso no transaccional a los archivos almacenados en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], debe especificar el nivel deseado de acceso no transaccional en el nivel de base de datos para cada base de datos que contenga FileTables.</span><span class="sxs-lookup"><span data-stu-id="666e5-126">To allow this non-transactional access to files stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you have to specify the desired level of non-transactional access at the database level for each database that will contain FileTables.</span></span>  
  
###  <a name="how-to-check-whether-non-transactional-access-is-enabled-on-databases"></a><a name="HowToCheckAccess"></a> <span data-ttu-id="666e5-127">Procedimientos para: comprobar si el acceso no transaccional está habilitado en las bases de datos</span><span class="sxs-lookup"><span data-stu-id="666e5-127">How To: Check Whether Non-Transactional Access Is Enabled on Databases</span></span>  
 <span data-ttu-id="666e5-128">Consulte la vista de catálogo [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) y compruebe las columnas **non_transacted_access** y **non_transacted_access_desc**.</span><span class="sxs-lookup"><span data-stu-id="666e5-128">Query the catalog view [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) and check the **non_transacted_access** and **non_transacted_access_desc** columns.</span></span>  
  
```sql  
SELECT DB_NAME(database_id), non_transacted_access, non_transacted_access_desc  
    FROM sys.database_filestream_options;  
GO  
```  
  
###  <a name="how-to-enable-non-transactional-access-at-the-database-level"></a><a name="HowToNTAccess"></a> <span data-ttu-id="666e5-129">Procedimientos para: habilitar el acceso no transaccional en el nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="666e5-129">How To: Enable Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="666e5-130">Los niveles disponibles de acceso no transaccional son FULL, READ_ONLY y OFF.</span><span class="sxs-lookup"><span data-stu-id="666e5-130">The available levels of non-transactional access are FULL, READ_ONLY, and OFF.</span></span>  
  
 <span data-ttu-id="666e5-131">**Especificar el nivel de acceso no transaccional mediante Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="666e5-131">**Specify the level of non-transactional access by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="666e5-132">Cuando **cree una base de datos nueva**, llame a la instrucción [CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) con la opción de FILESTREAM **NON_TRANSACTED_ACCESS**.</span><span class="sxs-lookup"><span data-stu-id="666e5-132">When you **create a new database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **NON_TRANSACTED_ACCESS** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        WITH FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' )  
    ```  
  
-   <span data-ttu-id="666e5-133">Cuando **modifique una base de datos existente**, llame a la instrucción [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) con la opción de FILESTREAM **NON_TRANSACTED_ACCESS**.</span><span class="sxs-lookup"><span data-stu-id="666e5-133">When you **alter an existing database**, call the [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) statement with the **NON_TRANSACTED_ACCESS** FILESTREAM option.</span></span>  
  
    ```sql  
    ALTER DATABASE database_name  
        SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' )  
    ```  
  
 <span data-ttu-id="666e5-134">**Especificar el nivel de acceso no transaccional mediante SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="666e5-134">**Specify the level of non-transactional access by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="666e5-135">Puede especificar el nivel de acceso no transaccional en el campo **Acceso sin transacciones de FILESTREAM** de la página **Opciones** del cuadro de diálogo **Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="666e5-135">You can specify the level of non-transactional access in the **FILESTREAM Non-transacted Access** field of the **Options** page of the **Database Properties** dialog box.</span></span> <span data-ttu-id="666e5-136">Para obtener más información sobre este cuadro de diálogo, vea [Propiedades de la base de datos &#40;página Opciones&#41;](../databases/database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="666e5-136">For more information about this dialog box, see [Database Properties &#40;Options Page&#41;](../databases/database-properties-options-page.md).</span></span>  
  
##  <a name="specifying-a-directory-for-filetables-at-the-database-level"></a><a name="BasicsDirectory"></a> <span data-ttu-id="666e5-137">Especificar un directorio para FileTables en el nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="666e5-137">Specifying a Directory for FileTables at the Database Level</span></span>  
 <span data-ttu-id="666e5-138">Cuando habilite el acceso no transaccional a archivos en el nivel de base de datos, puede indicar el nombre de un directorio opcionalmente al mismo tiempo mediante la opción **DIRECTORY_NAME** .</span><span class="sxs-lookup"><span data-stu-id="666e5-138">When you enable non-transactional access to files at the database level, you can optionally provide a directory name at the same time by using the **DIRECTORY_NAME** option.</span></span> <span data-ttu-id="666e5-139">Si no proporciona ningún directorio cuando habilite el acceso no transaccional, debe proporcionarlo posteriormente antes de que pueda crear FileTables en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="666e5-139">If you do not provide a directory name when you enable non-transactional access, then you have to provide it later before you can create FileTables in the database.</span></span>  
  
 <span data-ttu-id="666e5-140">En la jerarquía de carpetas de FileTable, este directorio de nivel de base de datos se convierte en el secundario del nombre del recurso compartido especificado para FILESTREAM en el nivel de instancia y en el primario de las FileTables creadas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="666e5-140">In the FileTable folder hierarchy, this database-level directory becomes the child of the share name specified for FILESTREAM at the instance level, and the parent of the FileTables created in the database.</span></span> <span data-ttu-id="666e5-141">Para más información, consulte [Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="666e5-141">For more information, see [Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md).</span></span>  
  
###  <a name="how-to-specify-a-directory-for-filetables-at-the-database-level"></a><a name="HowToDirectory"></a> <span data-ttu-id="666e5-142">Procedimientos para: especificar un directorio para FileTables en el nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="666e5-142">How To: Specify a Directory for FileTables at the Database Level</span></span>  
 <span data-ttu-id="666e5-143">El nombre que especifique debe ser único en toda la instancia para los directorios de base de datos.</span><span class="sxs-lookup"><span data-stu-id="666e5-143">The name that you specify must be unique across the instance for database-level directories.</span></span>  
  
 <span data-ttu-id="666e5-144">**Especificar un directorio para FileTables mediante Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="666e5-144">**Specify a directory for FileTables by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="666e5-145">Cuando **cree una base de datos nueva**, llame a la instrucción [CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) con la opción de FILESTREAM **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="666e5-145">When you **create a new database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        WITH FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="666e5-146">Cuando **modifique una base de datos existente**, llame a la instrucción [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) con la opción de FILESTREAM **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="666e5-146">When you **alter an existing database**, call the [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span> <span data-ttu-id="666e5-147">Cuando use estas opciones para cambiar el nombre del directorio, la base de datos se debe bloquear de forma exclusiva y sin identificadores de archivo abiertos.</span><span class="sxs-lookup"><span data-stu-id="666e5-147">When you use these options to change the directory name, the database must be exclusively locked, with no open file handles.</span></span>  
  
    ```sql  
    ALTER DATABASE database_name  
        SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="666e5-148">Cuando **adjunte una base de datos**, llame a la instrucción [CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) con la opción **FOR ATTACH** y con la opción FILESTREAM de **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="666e5-148">When you **attach a database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **FOR ATTACH** option and with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        FOR ATTACH WITH FILESTREAM ( DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="666e5-149">Cuando **restaure una base de datos**, llame a la instrucción [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) con la opción de FILESTREAM **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="666e5-149">When you **restore a database**, call the [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    RESTORE DATABASE database_name  
        WITH FILESTREAM ( DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
 <span data-ttu-id="666e5-150">**Especificar un directorio para las FileTables mediante SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="666e5-150">**Specify a directory for FileTables by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="666e5-151">Puede especificar el nombre de un directorio en el campo **Nombre de directorio de FILESTREAM** de la página **Opciones** del cuadro de diálogo **Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="666e5-151">You can specify a directory name in the **FILESTREAM Directory Name** field of the **Options** page of the **Database Properties** dialog box.</span></span> <span data-ttu-id="666e5-152">Para obtener más información sobre este cuadro de diálogo, vea [Propiedades de la base de datos &#40;página Opciones&#41;](../databases/database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="666e5-152">For more information about this dialog box, see [Database Properties &#40;Options Page&#41;](../databases/database-properties-options-page.md).</span></span>  
  
###  <a name="how-to-view-existing-directory-names-for-the-instance"></a><a name="viewnames"></a> <span data-ttu-id="666e5-153">Procedimientos para: ver los nombres de directorio existentes para la instancia</span><span class="sxs-lookup"><span data-stu-id="666e5-153">How to: View Existing Directory Names for the Instance</span></span>  
 <span data-ttu-id="666e5-154">Para ver la lista de nombres de directorio existentes de la instancia, consulte la vista de catálogo [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) y compruebe la columna **filestream_database_directory_name**.</span><span class="sxs-lookup"><span data-stu-id="666e5-154">To view the list of existing directory names for the instance, query the catalog view [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) and check the **filestream_database_directory_name** column.</span></span>  
  
```sql  
SELECT DB_NAME ( database_id ), directory_name  
    FROM sys.database_filestream_options;  
GO  
```  
  
###  <a name="requirements-and-restrictions-for-the-database-level-directory"></a><a name="ReqDirectory"></a> <span data-ttu-id="666e5-155">Requisitos y restricciones para el directorio de base de datos</span><span class="sxs-lookup"><span data-stu-id="666e5-155">Requirements and Restrictions for the Database-Level Directory</span></span>  
  
-   <span data-ttu-id="666e5-156">Establecer el valor de **DIRECTORY_NAME** es opcional cuando llame a **CREATE DATABASE** o a **ALTER DATABASE**.</span><span class="sxs-lookup"><span data-stu-id="666e5-156">Setting the **DIRECTORY_NAME** is optional when you call **CREATE DATABASE** or **ALTER DATABASE**.</span></span> <span data-ttu-id="666e5-157">Si no especifica ningún valor para **DIRECTORY_NAME**, el nombre del directorio continúa siendo NULL</span><span class="sxs-lookup"><span data-stu-id="666e5-157">If you do not specify a value for **DIRECTORY_NAME**, then the directory name remains null.</span></span> <span data-ttu-id="666e5-158">y no podrá crear FileTables en la base de datos hasta que especifique un valor para **DIRECTORY_NAME** en el nivel de base de datos.</span><span class="sxs-lookup"><span data-stu-id="666e5-158">However you cannot create FileTables in the database until you specify a value for **DIRECTORY_NAME** at the database level.</span></span>  
  
-   <span data-ttu-id="666e5-159">El nombre de directorio que proporcione debe cumplir los requisitos del sistema de archivos de un nombre de directorio válido.</span><span class="sxs-lookup"><span data-stu-id="666e5-159">The directory name that you provide must comply with the requirements of the file system for a valid directory name.</span></span>  
  
-   <span data-ttu-id="666e5-160">Cuando la base de datos contenga FileTables, no puede volver a establecer el valor de **DIRECTORY_NAME** en NULL.</span><span class="sxs-lookup"><span data-stu-id="666e5-160">When the database contains FileTables, you cannot set the **DIRECTORY_NAME** back to a null value.</span></span>  
  
-   <span data-ttu-id="666e5-161">Cuando adjunte o restaure una base de datos, se produce un error en la operación si la nueva base de datos tiene un valor para **DIRECTORY_NAME** que ya existe en la instancia de destino.</span><span class="sxs-lookup"><span data-stu-id="666e5-161">When you attach or restore a database, the operation fails if the new database has a value for **DIRECTORY_NAME** that already exists in the target instance.</span></span> <span data-ttu-id="666e5-162">Especifique un valor único para **DIRECTORY_NAME** cuando llame a **CREATE DATABASE FOR ATTACH** o a **RESTORE DATABASE**.</span><span class="sxs-lookup"><span data-stu-id="666e5-162">Specify a unique value for **DIRECTORY_NAME** when you call **CREATE DATABASE FOR ATTACH** or **RESTORE DATABASE**.</span></span>  
  
-   <span data-ttu-id="666e5-163">Cuando actualice una base de datos existente a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], el valor de **DIRECTORY_NAME** es NULL.</span><span class="sxs-lookup"><span data-stu-id="666e5-163">When you upgrade an existing database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the value of **DIRECTORY_NAME** is null.</span></span>  
  
-   <span data-ttu-id="666e5-164">Cuando habilite o deshabilite el acceso no transaccional en el nivel de base de datos, la operación no comprueba si se ha especificado el nombre del directorio o si es único.</span><span class="sxs-lookup"><span data-stu-id="666e5-164">When you enable or disable non-transactional access at the database level, the operation does not check whether the directory name has been specified or whether it is unique.</span></span>  
  
-   <span data-ttu-id="666e5-165">Cuando quite una base de datos habilitada para FileTables, se quitan el directorio de nivel de base de datos y todas las estructuras de directorio de todas las FileTables contenidas en él.</span><span class="sxs-lookup"><span data-stu-id="666e5-165">When you drop a database that was enabled for FileTables, the database-level directory and all the directory stuctures of all the FileTables under it are removed.</span></span>  
  
  
