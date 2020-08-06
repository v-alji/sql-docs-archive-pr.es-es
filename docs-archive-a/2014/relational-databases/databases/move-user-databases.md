---
title: Movimiento de bases de datos de usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- disaster recovery [SQL Server], moving database files
- database files [SQL Server], moving
- data files [SQL Server], moving
- editions [SQL Server], moving databases between
- moving full-text catalogs
- scheduled disk maintenace [SQL Server]
- moving databases
- full-text catalogs [SQL Server], moving
- moving database files
- moving user databases
- relocating database files
- planned database relocations [SQL Server]
- databases [SQL Server], moving
ms.assetid: ad9a4e92-13fb-457d-996a-66ffc2d55b79
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6c2b82c3bec13c82aa30aebd175ef78f8136ee04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672094"
---
# <a name="move-user-databases"></a><span data-ttu-id="313df-102">Mover bases de datos de usuario</span><span class="sxs-lookup"><span data-stu-id="313df-102">Move User Databases</span></span>
  <span data-ttu-id="313df-103">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], puede mover los archivos de datos, del registro y del catálogo de texto completo de una base de datos de usuario a una nueva ubicación, especificando la nueva ubicación en la cláusula FILENAME de la instrucción [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="313df-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can move the data, log, and full-text catalog files of a user database to a new location by specifying the new file location in the FILENAME clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="313df-104">Este método se aplica para mover archivos de la base de datos dentro de la misma instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="313df-104">This method applies to moving database files within the same instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="313df-105">Para mover una base de datos a otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o a otro servidor, use las operaciones de [copias de seguridad y restauración](../backup-restore/back-up-and-restore-of-sql-server-databases.md) o [separar y adjuntar](move-a-database-using-detach-and-attach-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="313df-105">To move a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to another server, use [backup and restore](../backup-restore/back-up-and-restore-of-sql-server-databases.md) or [detach and attach operations](move-a-database-using-detach-and-attach-transact-sql.md).</span></span>  
  
## <a name="considerations"></a><span data-ttu-id="313df-106">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="313df-106">Considerations</span></span>  
 <span data-ttu-id="313df-107">Al mover una base de datos a otra instancia de servidor, para proporcionar una experiencia coherente a usuarios y aplicaciones, puede que tenga que volver a crear algunos o todos los metadatos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="313df-107">When you move a database onto another server instance, to provide a consistent experience to users and applications, you might have to re-create some or all the metadata for the database.</span></span> <span data-ttu-id="313df-108">Para obtener más información, vea [Administrar los metadatos cuando una base de datos pasa a estar disponible en otra instancia del servidor &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="313df-108">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
 <span data-ttu-id="313df-109">Algunas características de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] cambian la manera en que el [!INCLUDE[ssDE](../../includes/ssde-md.md)] almacena información en los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="313df-109">Some features of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] change the way that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores information in the database files.</span></span> <span data-ttu-id="313df-110">Estas características están restringidas a ediciones concretas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="313df-110">These features are restricted to specific editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="313df-111">Una base de datos que contiene estas características no se puede mover a una edición de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que no los admita.</span><span class="sxs-lookup"><span data-stu-id="313df-111">A database that contains these features cannot be moved to an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that does not support them.</span></span> <span data-ttu-id="313df-112">Utilice la vista de administración dinámica sys.dm_db_persisted_sku_features para enumerar todas las características específicas de la edición que estén habilitadas en la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="313df-112">Use the sys.dm_db_persisted_sku_features dynamic management view to list all edition-specific features that are enabled in the current database.</span></span>  
  
 <span data-ttu-id="313df-113">Los procedimientos descritos en este tema requieren el nombre lógico de los archivos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="313df-113">The procedures in this topic require the logical name of the database files.</span></span> <span data-ttu-id="313df-114">Para obtener el nombre, consulte la columna de nombre de la vista de catálogo [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="313df-114">To obtain the name, query the name column in the [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="313df-115">A partir de [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], los catálogos de texto completo se integran en la base de datos, en lugar de almacenarse en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="313df-115">Starting with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], full-text catalogs are integrated into the database rather than being stored in the file system.</span></span> <span data-ttu-id="313df-116">Los catálogos de texto completo se mueven ahora automáticamente al mover una base de datos.</span><span class="sxs-lookup"><span data-stu-id="313df-116">The full-text catalogs now move automatically when you move a database.</span></span>  
  
## <a name="planned-relocation-procedure"></a><span data-ttu-id="313df-117">Procedimiento de reubicación planeada</span><span class="sxs-lookup"><span data-stu-id="313df-117">Planned Relocation Procedure</span></span>  
 <span data-ttu-id="313df-118">Para mover un archivo de datos o de registros como parte de una reubicación planeada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="313df-118">To move a data or log file as part of a planned relocation, follow these steps:</span></span>  
  
1.  <span data-ttu-id="313df-119">Ejecute la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="313df-119">Run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name SET OFFLINE;  
    ```  
  
2.  <span data-ttu-id="313df-120">Mueva el archivo o los archivos a la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="313df-120">Move the file or files to the new location.</span></span>  
  
3.  <span data-ttu-id="313df-121">Con cada archivo que mueva, ejecute la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="313df-121">For each file moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name, FILENAME = 'new_path\os_file_name' );  
    ```  
  
4.  <span data-ttu-id="313df-122">Ejecute la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="313df-122">Run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name SET ONLINE;  
    ```  
  
5.  <span data-ttu-id="313df-123">Compruebe el cambio de los archivos ejecutando la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="313df-123">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="relocation-for-scheduled-disk-maintenance"></a><span data-ttu-id="313df-124">Reubicación para el mantenimiento planeado del disco</span><span class="sxs-lookup"><span data-stu-id="313df-124">Relocation for Scheduled Disk Maintenance</span></span>  
 <span data-ttu-id="313df-125">Para reubicar un archivo como parte de un proceso de mantenimiento planeado del disco, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="313df-125">To relocate a file as part of a scheduled disk maintenance process, follow these steps:</span></span>  
  
1.  <span data-ttu-id="313df-126">Para cada archivo que se va a mover, ejecute la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="313df-126">For each file to be moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name , FILENAME = 'new_path\os_file_name' );  
    ```  
  
2.  <span data-ttu-id="313df-127">Detenga la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o cierre el sistema para realizar el mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="313df-127">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or shut down the system to perform maintenance.</span></span> <span data-ttu-id="313df-128">Para más información, consulte [Iniciar, detener, pausar, reanudar y reiniciar el motor de base de datos, Agente SQL Server o el Servicio SQL Server Browser](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="313df-128">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="313df-129">Mueva el archivo o los archivos a la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="313df-129">Move the file or files to the new location.</span></span>  
  
4.  <span data-ttu-id="313df-130">Reinicie la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o el servidor.</span><span class="sxs-lookup"><span data-stu-id="313df-130">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the server.</span></span> <span data-ttu-id="313df-131">Para obtener más información, consulte [Iniciar, detener, pausar, reanudar y reiniciar el motor de base de datos, Agente SQL Server o el Servicio SQL Server Browser](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="313df-131">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)</span></span>  
  
5.  <span data-ttu-id="313df-132">Compruebe el cambio de los archivos ejecutando la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="313df-132">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="failure-recovery-procedure"></a><span data-ttu-id="313df-133">Procedimiento de recuperación de errores</span><span class="sxs-lookup"><span data-stu-id="313df-133">Failure Recovery Procedure</span></span>  
 <span data-ttu-id="313df-134">Si se debe mover un archivo a causa de un error de hardware, siga los pasos que se indican a continuación para reubicar el archivo.</span><span class="sxs-lookup"><span data-stu-id="313df-134">If a file must be moved because of a hardware failure, use the following steps to relocate the file to a new location.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="313df-135">Si no se puede iniciar la base de datos, es decir, si se encuentra en modo sospechoso o en un estado no recuperado, solo los miembros del rol fijo sysadmin podrán mover el archivo.</span><span class="sxs-lookup"><span data-stu-id="313df-135">If the database cannot be started, that is it is in suspect mode or in an unrecovered state, only members of the sysadmin fixed role can move the file.</span></span>  
  
1.  <span data-ttu-id="313df-136">Detenga la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si se inició.</span><span class="sxs-lookup"><span data-stu-id="313df-136">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if it is started.</span></span>  
  
2.  <span data-ttu-id="313df-137">Inicie la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en modo de recuperación solo de master especificando uno de los siguientes comandos en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="313df-137">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in master-only recovery mode by entering one of the following commands at the command prompt.</span></span>  
  
    -   <span data-ttu-id="313df-138">Para una instancia predeterminada (MSSQLSERVER), ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="313df-138">For the default (MSSQLSERVER) instance, run the following command.</span></span>  
  
        ```  
        NET START MSSQLSERVER /f /T3608  
        ```  
  
    -   <span data-ttu-id="313df-139">Para una instancia con nombre, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="313df-139">For a named instance, run the following command.</span></span>  
  
        ```  
        NET START MSSQL$instancename /f /T3608  
        ```  
  
     <span data-ttu-id="313df-140">Para más información, consulte [Iniciar, detener, pausar, reanudar y reiniciar el motor de base de datos, Agente SQL Server o el Servicio SQL Server Browser](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="313df-140">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="313df-141">En cada uno de los archivos que se van a mover, use los comandos **sqlcmd** o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] para ejecutar la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="313df-141">For each file to be moved, use **sqlcmd** commands or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE( NAME = logical_name , FILENAME = 'new_path\os_file_name' );  
    ```  
  
     <span data-ttu-id="313df-142">Para obtener más información sobre cómo usar la utilidad **sqlcmd** , vea [Usar la utilidad sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="313df-142">For more information about how to use the **sqlcmd** utility, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
4.  <span data-ttu-id="313df-143">Salga de la utilidad **sqlcmd** o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="313df-143">Exit the **sqlcmd** utility or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
5.  <span data-ttu-id="313df-144">Detenga la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="313df-144">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
6.  <span data-ttu-id="313df-145">Mueva el archivo o los archivos a la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="313df-145">Move the file or files to the new location.</span></span>  
  
7.  <span data-ttu-id="313df-146">Inicie la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="313df-146">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="313df-147">Por ejemplo, ejecute: `NET START MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="313df-147">For example, run: `NET START MSSQLSERVER`.</span></span>  
  
8.  <span data-ttu-id="313df-148">Compruebe el cambio de los archivos ejecutando la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="313df-148">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="examples"></a><span data-ttu-id="313df-149">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="313df-149">Examples</span></span>  
 <span data-ttu-id="313df-150">En el ejemplo siguiente se mueve el archivo de registro [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] a la nueva ubicación como parte de una reubicación planeada.</span><span class="sxs-lookup"><span data-stu-id="313df-150">The following example moves the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] log file to a new location as part of a planned relocation.</span></span>  
  
```  
USE master;  
GO  
-- Return the logical file name.  
SELECT name, physical_name AS CurrentLocation, state_desc  
FROM sys.master_files  
WHERE database_id = DB_ID(N'AdventureWorks2012')  
    AND type_desc = N'LOG';  
GO  
ALTER DATABASE AdventureWorks2012 SET OFFLINE;  
GO  
-- Physically move the file to a new location.  
-- In the following statement, modify the path specified in FILENAME to  
-- the new location of the file on your server.  
ALTER DATABASE AdventureWorks2012   
    MODIFY FILE ( NAME = AdventureWorks2012_Log,   
                  FILENAME = 'C:\NewLoc\AdventureWorks2012_Log.ldf');  
GO  
ALTER DATABASE AdventureWorks2012 SET ONLINE;  
GO  
--Verify the new location.  
SELECT name, physical_name AS CurrentLocation, state_desc  
FROM sys.master_files  
WHERE database_id = DB_ID(N'AdventureWorks2012')  
    AND type_desc = N'LOG';  
```  
  
## <a name="see-also"></a><span data-ttu-id="313df-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="313df-151">See Also</span></span>  
 <span data-ttu-id="313df-152">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="313df-152">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="313df-153">[CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="313df-153">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="313df-154">[Adjuntar y separar bases de datos &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="313df-154">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="313df-155">[Mover bases de datos del sistema](system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="313df-155">[Move System Databases](system-databases.md) </span></span>  
 <span data-ttu-id="313df-156">[Mover archivos de base de datos](move-database-files.md) </span><span class="sxs-lookup"><span data-stu-id="313df-156">[Move Database Files](move-database-files.md) </span></span>  
 <span data-ttu-id="313df-157">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="313df-157">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="313df-158">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="313df-158">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="313df-159">Iniciar, detener, pausar, reanudar y reiniciar el motor de base de datos, Agente SQL Server o el Servicio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="313df-159">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
  
