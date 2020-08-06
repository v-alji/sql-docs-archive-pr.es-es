---
title: Movimiento de bases de datos del sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- moving system databases
- disaster recovery [SQL Server], moving database files
- database files [SQL Server], moving
- data files [SQL Server], moving
- tempdb database [SQL Server], moving
- system databases [SQL Server], moving
- scheduled disk maintenace [SQL Server]
- moving databases
- msdb database [SQL Server], moving
- moving database files
- relocating database files
- planned database relocations [SQL Server]
- master database [SQL Server], moving
- model database [SQL Server], moving
- Resource database [SQL Server]
- databases [SQL Server], moving
ms.assetid: 72bb62ee-9602-4f71-be51-c466c1670878
author: stevestein
ms.author: sstein
ms.openlocfilehash: 748d781d6bbefb0dc710427a34ebd71ec7037fdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752226"
---
# <a name="move-system-databases"></a><span data-ttu-id="219f0-102">Mover bases de datos del sistema</span><span class="sxs-lookup"><span data-stu-id="219f0-102">Move System Databases</span></span>
  <span data-ttu-id="219f0-103">En este tema se describe cómo mover bases de datos del sistema en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="219f0-103">This topic describes how to move system databases in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="219f0-104">Mover bases de datos del sistema puede resultar útil en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="219f0-104">Moving system databases may be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="219f0-105">Recuperación de un error.</span><span class="sxs-lookup"><span data-stu-id="219f0-105">Failure recovery.</span></span> <span data-ttu-id="219f0-106">Por ejemplo, la base de datos se encuentra en modo sospechoso o se ha cerrado a causa de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="219f0-106">For example, the database is in suspect mode or has shut down because of a hardware failure.</span></span>  
  
-   <span data-ttu-id="219f0-107">Reubicación planeada.</span><span class="sxs-lookup"><span data-stu-id="219f0-107">Planned relocation.</span></span>  
  
-   <span data-ttu-id="219f0-108">Reubicación para el mantenimiento planeado del disco.</span><span class="sxs-lookup"><span data-stu-id="219f0-108">Relocation for scheduled disk maintenance.</span></span>  
  
 <span data-ttu-id="219f0-109">Los siguientes procedimientos se aplican para mover archivos de base de datos dentro de una misma instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="219f0-109">The following procedures apply to moving database files within the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="219f0-110">Para mover una base de datos a otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o a otro servidor, utilice las operaciones [copias de seguridad y restauración](../backup-restore/back-up-and-restore-of-sql-server-databases.md) o [separar y adjuntar](move-a-database-using-detach-and-attach-transact-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="219f0-110">To move a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to another server, use the [backup and restore](../backup-restore/back-up-and-restore-of-sql-server-databases.md) or [detach and attach](move-a-database-using-detach-and-attach-transact-sql.md) operations.</span></span>  
  
 <span data-ttu-id="219f0-111">Los procedimientos descritos en este tema requieren el nombre lógico de los archivos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="219f0-111">The procedures in this topic require the logical name of the database files.</span></span> <span data-ttu-id="219f0-112">Para obtener el nombre, consulte la columna de nombre de la vista de catálogo [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="219f0-112">To obtain the name, query the name column in the [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) catalog view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="219f0-113">Si se mueve una base de datos del sistema y posteriormente se vuelve a generar la base de datos maestra, se debe mover de nuevo la base de datos del sistema porque la operación de regeneración instala todas las bases de datos del sistema en su ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="219f0-113">If you move a system database and later rebuild the master database, you must move the system database again because the rebuild operation installs all system databases to their default location.</span></span>  
  
##  <a name="in-this-topic"></a><a name="Intro"></a><span data-ttu-id="219f0-114">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="219f0-114">**In This Topic**</span></span>  
  
-   [<span data-ttu-id="219f0-115">Procedimiento de reubicación planeada y mantenimiento de disco programado</span><span class="sxs-lookup"><span data-stu-id="219f0-115">Planned Relocation and Scheduled Disk Maintenance Procedure</span></span>](#Planned)  
  
-   [<span data-ttu-id="219f0-116">Procedimiento de recuperación de errores</span><span class="sxs-lookup"><span data-stu-id="219f0-116">Failure Recovery Procedure</span></span>](#Failure)  
  
-   [<span data-ttu-id="219f0-117">Mover la base de datos maestra</span><span class="sxs-lookup"><span data-stu-id="219f0-117">Moving the master Database</span></span>](#master)  
  
-   [<span data-ttu-id="219f0-118">Mover la base de datos Resource</span><span class="sxs-lookup"><span data-stu-id="219f0-118">Moving the Resource Database</span></span>](#Resource)  
  
-   [<span data-ttu-id="219f0-119">Seguimiento: después de mover todas las bases de datos del sistema</span><span class="sxs-lookup"><span data-stu-id="219f0-119">Follow-up: After Moving All System Databases</span></span>](#Follow)  
  
-   [<span data-ttu-id="219f0-120">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="219f0-120">Examples</span></span>](#Examples)  
  
##  <a name="planned-relocation-and-scheduled-disk-maintenance-procedure"></a><a name="Planned"></a> <span data-ttu-id="219f0-121">Procedimiento de reubicación planeada y mantenimiento de disco programado</span><span class="sxs-lookup"><span data-stu-id="219f0-121">Planned Relocation and Scheduled Disk Maintenance Procedure</span></span>  
 <span data-ttu-id="219f0-122">Para mover un archivo de registro o datos de bases de datos del sistema como parte de una operación de reubicación planeada o de mantenimiento programado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="219f0-122">To move a system database data or log file as part of a planned relocation or scheduled maintenance operation, follow these steps.</span></span> <span data-ttu-id="219f0-123">Este procedimiento se aplica a todas las bases de datos del sistema, excepto las bases de datos maestras y Resource.</span><span class="sxs-lookup"><span data-stu-id="219f0-123">This procedure applies to all system databases except the master and Resource databases.</span></span>  
  
1.  <span data-ttu-id="219f0-124">Para cada archivo que se va a mover, ejecute la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="219f0-124">For each file to be moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name , FILENAME = 'new_path\os_file_name' )  
    ```  
  
2.  <span data-ttu-id="219f0-125">Detenga la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o cierre el sistema para realizar el mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="219f0-125">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or shut down the system to perform maintenance.</span></span> <span data-ttu-id="219f0-126">Para más información, consulte [Iniciar, detener, pausar, reanudar y reiniciar el motor de base de datos, Agente SQL Server o el Servicio SQL Server Browser](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="219f0-126">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="219f0-127">Mueva el archivo o los archivos a la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="219f0-127">Move the file or files to the new location.</span></span>  
  
4.  <span data-ttu-id="219f0-128">Reinicie la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o el servidor.</span><span class="sxs-lookup"><span data-stu-id="219f0-128">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the server.</span></span> <span data-ttu-id="219f0-129">Para más información, consulte [Iniciar, detener, pausar, reanudar y reiniciar el motor de base de datos, Agente SQL Server o el Servicio SQL Server Browser](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="219f0-129">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
5.  <span data-ttu-id="219f0-130">Compruebe el cambio de los archivos ejecutando la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="219f0-130">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
 <span data-ttu-id="219f0-131">Si se mueve la base de datos msdb y se configura la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para [Correo electrónico de base de datos](../database-mail/database-mail.md), complete estos pasos adicionales.</span><span class="sxs-lookup"><span data-stu-id="219f0-131">If the msdb database is moved and the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured for [Database Mail](../database-mail/database-mail.md), complete these additional steps.</span></span>  
  
1.  <span data-ttu-id="219f0-132">Compruebe que [!INCLUDE[ssSB](../../../includes/sssb-md.md)] se haya habilitado para la base de datos msdb; para ello, ejecute la siguiente consulta.</span><span class="sxs-lookup"><span data-stu-id="219f0-132">Verify that [!INCLUDE[ssSB](../../../includes/sssb-md.md)] is enabled for the msdb database by running the following query.</span></span>  
  
    ```  
    SELECT is_broker_enabled   
    FROM sys.databases  
    WHERE name = N'msdb';  
    ```  
  
     <span data-ttu-id="219f0-133">Para obtener más información sobre cómo habilitar [!INCLUDE[ssSB](../../../includes/sssb-md.md)], vea [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="219f0-133">For more information about enabling [!INCLUDE[ssSB](../../../includes/sssb-md.md)], see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
2.  <span data-ttu-id="219f0-134">Envíe un mensaje de correo electrónico para comprobar que el Correo electrónico de base de datos funciona.</span><span class="sxs-lookup"><span data-stu-id="219f0-134">Verify that Database Mail is working by sending a test mail.</span></span>  
  
##  <a name="failure-recovery-procedure"></a><a name="Failure"></a> <span data-ttu-id="219f0-135">Procedimiento de recuperación de errores</span><span class="sxs-lookup"><span data-stu-id="219f0-135">Failure Recovery Procedure</span></span>  
 <span data-ttu-id="219f0-136">Si se debe mover un archivo a causa de un error de hardware, siga los pasos que se indican a continuación para colocar el archivo en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="219f0-136">If a file must be moved because of a hardware failure, follow these steps to relocate the file to a new location.</span></span> <span data-ttu-id="219f0-137">Este procedimiento se aplica a todas las bases de datos del sistema, excepto las bases de datos maestras y Resource.</span><span class="sxs-lookup"><span data-stu-id="219f0-137">This procedure applies to all system databases except the master and Resource databases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="219f0-138">Si no se puede iniciar la base de datos, es decir, si se encuentra en modo sospechoso o en un estado no recuperado, solo los miembros del rol fijo sysadmin podrán mover el archivo.</span><span class="sxs-lookup"><span data-stu-id="219f0-138">If the database cannot be started, that is it is in suspect mode or in an unrecovered state, only members of the sysadmin fixed role can move the file.</span></span>  
  
1.  <span data-ttu-id="219f0-139">Detenga la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si se inició.</span><span class="sxs-lookup"><span data-stu-id="219f0-139">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if it is started.</span></span>  
  
2.  <span data-ttu-id="219f0-140">Inicie la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en modo de recuperación solo de master especificando uno de los siguientes comandos en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="219f0-140">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in master-only recovery mode by entering one of the following commands at the command prompt.</span></span> <span data-ttu-id="219f0-141">Los parámetros especificados en estos comandos distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="219f0-141">The parameters specified in these commands are case sensitive.</span></span> <span data-ttu-id="219f0-142">Los comandos generan un error cuando los parámetros no se especifican como se indica.</span><span class="sxs-lookup"><span data-stu-id="219f0-142">The commands fail when the parameters are not specified as shown.</span></span>  
  
    -   <span data-ttu-id="219f0-143">Para la instancia predeterminada (MSSQLSERVER), ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="219f0-143">For the default (MSSQLSERVER) instance, run the following command:</span></span>  
  
        ```  
        NET START MSSQLSERVER /f /T3608  
        ```  
  
    -   <span data-ttu-id="219f0-144">Para una instancia con nombre, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="219f0-144">For a named instance, run the following command:</span></span>  
  
        ```  
        NET START MSSQL$instancename /f /T3608  
        ```  
  
     <span data-ttu-id="219f0-145">Para más información, consulte [Iniciar, detener, pausar, reanudar y reiniciar el motor de base de datos, Agente SQL Server o el Servicio SQL Server Browser](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="219f0-145">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="219f0-146">En cada uno de los archivos que se van a mover, use los comandos **sqlcmd** o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] para ejecutar la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="219f0-146">For each file to be moved, use **sqlcmd** commands or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE( NAME = logical_name , FILENAME = 'new_path\os_file_name' )  
    ```  
  
     <span data-ttu-id="219f0-147">Para obtener más información sobre cómo usar la utilidad **sqlcmd** , vea [Usar la utilidad sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="219f0-147">For more information about using the **sqlcmd** utility, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
4.  <span data-ttu-id="219f0-148">Salga de la utilidad **sqlcmd** o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="219f0-148">Exit the **sqlcmd** utility or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
5.  <span data-ttu-id="219f0-149">Detenga la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="219f0-149">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="219f0-150">Por ejemplo, ejecute `NET STOP MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="219f0-150">For example, run `NET STOP MSSQLSERVER`.</span></span>  
  
6.  <span data-ttu-id="219f0-151">Mueva el archivo o los archivos a la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="219f0-151">Move the file or files to the new location.</span></span>  
  
7.  <span data-ttu-id="219f0-152">Reinicie la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="219f0-152">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="219f0-153">Por ejemplo, ejecute `NET START MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="219f0-153">For example, run `NET START MSSQLSERVER`.</span></span>  
  
8.  <span data-ttu-id="219f0-154">Compruebe el cambio de los archivos ejecutando la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="219f0-154">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
##  <a name="moving-the-master-database"></a><a name="master"></a> <span data-ttu-id="219f0-155">Mover la base de datos maestra</span><span class="sxs-lookup"><span data-stu-id="219f0-155">Moving the master Database</span></span>  
 <span data-ttu-id="219f0-156">Para mover la base de datos maestra, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="219f0-156">To move the master database, follow these steps.</span></span>  
  
1.  <span data-ttu-id="219f0-157">Desde el menú **Inicio** , seleccione **Todos los programas**, **Microsoft SQL Server 2005**, **Herramientas de configuración**y, finalmente, haga clic en **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="219f0-157">From the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="219f0-158">En el nodo **Servicios de SQL Server** , haga clic con el botón derecho en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (por ejemplo, **SQL Server (MSSQLSERVER)** ) y elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="219f0-158">In the **SQL Server Services** node, right-click the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (for example, **SQL Server (MSSQLSERVER)**) and choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="219f0-159">En el cuadro de diálogo \*\*Propiedades de ( \*\*\*nombre_de_instancia \***) de SQL Server** , haga clic en la pestaña **Parámetros de inicio** .</span><span class="sxs-lookup"><span data-stu-id="219f0-159">In the **SQL Server (***instance_name***) Properties** dialog box, click the **Startup Parameters** tab.</span></span>  
  
4.  <span data-ttu-id="219f0-160">En el cuadro **Parámetros existentes**, seleccione el parámetro -d para mover el archivo de datos maestros.</span><span class="sxs-lookup"><span data-stu-id="219f0-160">In the **Existing parameters** box, select the -d parameter to move the master data file.</span></span> <span data-ttu-id="219f0-161">Haga clic en **Actualizar** para guardar el cambio.</span><span class="sxs-lookup"><span data-stu-id="219f0-161">Click **Update** to save the change.</span></span>  
  
     <span data-ttu-id="219f0-162">En el cuadro **Especifique un parámetro de inicio** , cambie el parámetro a la nueva ruta de acceso de la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="219f0-162">In the **Specify a startup parameter** box, change the parameter to the new path of the master database.</span></span>  
  
5.  <span data-ttu-id="219f0-163">En el cuadro **Parámetros existentes**, seleccione el parámetro -l para mover el archivo de registro maestro.</span><span class="sxs-lookup"><span data-stu-id="219f0-163">In the **Existing parameters** box, select the -l parameter to move the master log file.</span></span> <span data-ttu-id="219f0-164">Haga clic en **Actualizar** para guardar el cambio.</span><span class="sxs-lookup"><span data-stu-id="219f0-164">Click **Update** to save the change.</span></span>  
  
     <span data-ttu-id="219f0-165">En el cuadro **Especifique un parámetro de inicio** , cambie el parámetro a la nueva ruta de acceso de la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="219f0-165">In the **Specify a startup parameter** box, change the parameter to the new path of the master database.</span></span>  
  
     <span data-ttu-id="219f0-166">El valor de parámetro del archivo de datos debe ir a continuación del parámetro `-d` y el valor del archivo de registro debe ir a continuación del parámetro `-l` .</span><span class="sxs-lookup"><span data-stu-id="219f0-166">The parameter value for the data file must follow the `-d` parameter and the value for the log file must follow the `-l` parameter.</span></span> <span data-ttu-id="219f0-167">En el siguiente ejemplo se muestran los valores de los parámetros para la ubicación predeterminada del archivo de datos maestros.</span><span class="sxs-lookup"><span data-stu-id="219f0-167">The following example shows the parameter values for the default location of the master data file.</span></span>  
  
     `-dC:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\master.mdf`  
  
     `-lC:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\mastlog.ldf`  
  
     <span data-ttu-id="219f0-168">Si la reubicación planeada para el archivo de datos maestros es `E:\SQLData`, los valores de parámetros se cambiarán de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="219f0-168">If the planned relocation for the master data file is `E:\SQLData`, the parameter values would be changed as follows:</span></span>  
  
     `-dE:\SQLData\master.mdf`  
  
     `-lE:\SQLData\mastlog.ldf`  
  
6.  <span data-ttu-id="219f0-169">Para detener la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , haga clic con el botón derecho en el nombre de la instancia y elija **Detener**.</span><span class="sxs-lookup"><span data-stu-id="219f0-169">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by right-clicking the instance name and choosing **Stop**.</span></span>  
  
7.  <span data-ttu-id="219f0-170">Mueva los archivos master.mdf y mastlog.ldf a la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="219f0-170">Move the master.mdf and mastlog.ldf files to the new location.</span></span>  
  
8.  <span data-ttu-id="219f0-171">Reinicie la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="219f0-171">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
9. <span data-ttu-id="219f0-172">Compruebe el cambio de archivo de la base de datos maestra ejecutando la siguiente consulta.</span><span class="sxs-lookup"><span data-stu-id="219f0-172">Verify the file change for the master database by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID('master');  
    GO  
    ```  
  
##  <a name="moving-the-resource-database"></a><a name="Resource"></a> <span data-ttu-id="219f0-173">Mover la base de datos Resource</span><span class="sxs-lookup"><span data-stu-id="219f0-173">Moving the Resource Database</span></span>  
 <span data-ttu-id="219f0-174">La ubicación de la base de datos Resource es \<*drive*>:\Archivos de programa\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\\.</span><span class="sxs-lookup"><span data-stu-id="219f0-174">The location of the Resource database is \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\\.</span></span> <span data-ttu-id="219f0-175">No se puede mover la base de datos.</span><span class="sxs-lookup"><span data-stu-id="219f0-175">The database cannot be moved.</span></span>  
  
##  <a name="follow-up-after-moving-all-system-databases"></a><a name="Follow"></a> <span data-ttu-id="219f0-176">Seguimiento: después de mover todas las bases de datos del sistema</span><span class="sxs-lookup"><span data-stu-id="219f0-176">Follow-up: After Moving All System Databases</span></span>  
 <span data-ttu-id="219f0-177">Si ha movido todas las bases de datos del sistema a una nueva unidad o volumen o a otro servidor con una letra de unidad diferente, realice las actualizaciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="219f0-177">If you have moved all of the system databases to a new drive or volume or to another server with a different drive letter, make the following updates.</span></span>  
  
-   <span data-ttu-id="219f0-178">Cambie la ruta de acceso del registro del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="219f0-178">Change the SQL Server Agent log path.</span></span> <span data-ttu-id="219f0-179">Si no actualiza esta ruta de acceso, el Agente SQL Server no se podrá iniciar.</span><span class="sxs-lookup"><span data-stu-id="219f0-179">If you do not update this path, SQL Server Agent will fail to start.</span></span>  
  
-   <span data-ttu-id="219f0-180">Cambie la ubicación predeterminada de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="219f0-180">Change the database default location.</span></span> <span data-ttu-id="219f0-181">Si la letra de unidad y la ruta de acceso especificada como ubicación predeterminada no existen, es posible que no se pueda crear una nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="219f0-181">Creating a new database may fail if the drive letter and path specified as the default location do not exist.</span></span>  
  
#### <a name="change-the-sql-server-agent-log-path"></a><span data-ttu-id="219f0-182">Cambiar la ruta de acceso del registro del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="219f0-182">Change the SQL Server Agent Log Path</span></span>  
  
1.  <span data-ttu-id="219f0-183">En SQL Server Management Studio, en el Explorador de objetos, expanda **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="219f0-183">From SQL Server Management Studio, in Object Explorer, expand **SQL Server Agent**.</span></span>  
  
2.  <span data-ttu-id="219f0-184">Haga clic con el botón derecho en **Registros de errores** y haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="219f0-184">Right-click **Error Logs** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="219f0-185">En el cuadro de diálogo **Configurar registros de errores del Agente SQL Server** , especifique la nueva ubicación del archivo SQLAGENT.OUT.</span><span class="sxs-lookup"><span data-stu-id="219f0-185">In the **Configure SQL Server Agent Error Logs** dialog box, specify the new location of the SQLAGENT.OUT file.</span></span> <span data-ttu-id="219f0-186">La ubicación predeterminada es C:\Archivos de Programa\microsoft SQL Server\MSSQL12. <instance_name> \Mssql\log. \\ .</span><span class="sxs-lookup"><span data-stu-id="219f0-186">The default location is C:\Program Files\Microsoft SQL Server\MSSQL12.<instance_name>\MSSQL\Log\\.</span></span>  
  
#### <a name="change-the-database-default-location"></a><span data-ttu-id="219f0-187">Cambiar la ubicación predeterminada de la base de datos</span><span class="sxs-lookup"><span data-stu-id="219f0-187">Change the database default location</span></span>  
  
1.  <span data-ttu-id="219f0-188">En SQL Server Management Studio, en el Explorador de objetos, haga clic con el botón derecho en el servidor de SQL Server y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="219f0-188">From SQL Server Management Studio, in Object Explorer, right-click the SQL Server server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="219f0-189">En el cuadro de diálogo **Propiedades del servidor** , seleccione **Configuración de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="219f0-189">In the **Server Properties** dialog box, select **Database Settings**.</span></span>  
  
3.  <span data-ttu-id="219f0-190">En **Ubicaciones predeterminadas de la base de datos**, busque la nueva ubicación de los archivos de registro y datos.</span><span class="sxs-lookup"><span data-stu-id="219f0-190">Under **Database Default Locations**, browse to the new location for both the data and log files.</span></span>  
  
4.  <span data-ttu-id="219f0-191">Detenga e inicie el servicio SQL Server para completar el cambio.</span><span class="sxs-lookup"><span data-stu-id="219f0-191">Stop and start the SQL Server service to complete the change.</span></span>  
  
##  <a name="examples"></a><a name="Examples"></a> <span data-ttu-id="219f0-192">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="219f0-192">Examples</span></span>  
  
### <a name="a-moving-the-tempdb-database"></a><span data-ttu-id="219f0-193">A.</span><span class="sxs-lookup"><span data-stu-id="219f0-193">A.</span></span> <span data-ttu-id="219f0-194">Mover la base de datos tempdb</span><span class="sxs-lookup"><span data-stu-id="219f0-194">Moving the tempdb database</span></span>  
 <span data-ttu-id="219f0-195">En el ejemplo siguiente se mueven los archivos de datos y registro de `tempdb` a una nueva ubicación como parte de una reubicación planeada.</span><span class="sxs-lookup"><span data-stu-id="219f0-195">The following example moves the `tempdb` data and log files to a new location as part of a planned relocation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="219f0-196">Puesto que tempdb se vuelve a crear cada vez que se inicia la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , no hay que mover físicamente los archivos de datos y registro.</span><span class="sxs-lookup"><span data-stu-id="219f0-196">Because tempdb is re-created each time the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started, you do not have to physically move the data and log files.</span></span> <span data-ttu-id="219f0-197">Los archivos se crean en la ubicación nueva cuando se reinicia el servicio en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="219f0-197">The files are created in the new location when the service is restarted in step 3.</span></span> <span data-ttu-id="219f0-198">Hasta que se reinicie el servicio, tempdb continúa utilizando los archivos de datos y de registro de la ubicación existente.</span><span class="sxs-lookup"><span data-stu-id="219f0-198">Until the service is restarted, tempdb continues to use the data and log files in existing location.</span></span>  
  
1.  <span data-ttu-id="219f0-199">Determine los nombres de los archivos lógicos de la base de datos `tempdb` y su ubicación actual en el disco.</span><span class="sxs-lookup"><span data-stu-id="219f0-199">Determine the logical file names of the `tempdb` database and their current location on the disk.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'tempdb');  
    GO  
    ```  
  
2.  <span data-ttu-id="219f0-200">Cambie la ubicación de cada archivo con `ALTER DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="219f0-200">Change the location of each file by using `ALTER DATABASE`.</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE tempdb   
    MODIFY FILE (NAME = tempdev, FILENAME = 'E:\SQLData\tempdb.mdf');  
    GO  
    ALTER DATABASE tempdb   
    MODIFY FILE (NAME = templog, FILENAME = 'F:\SQLLog\templog.ldf');  
    GO  
    ```  
  
3.  <span data-ttu-id="219f0-201">Detenga y reinicie la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="219f0-201">Stop and restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="219f0-202">Compruebe el cambio de los archivos.</span><span class="sxs-lookup"><span data-stu-id="219f0-202">Verify the file change.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'tempdb');  
    ```  
  
5.  <span data-ttu-id="219f0-203">Elimine los archivos `tempdb.mdf` y `templog.ldf` de la ubicación original.</span><span class="sxs-lookup"><span data-stu-id="219f0-203">Delete the `tempdb.mdf` and `templog.ldf` files from the original location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="219f0-204">Consulte también</span><span class="sxs-lookup"><span data-stu-id="219f0-204">See Also</span></span>  
 <span data-ttu-id="219f0-205">[Base de datos Resource](resource-database.md) </span><span class="sxs-lookup"><span data-stu-id="219f0-205">[Resource Database](resource-database.md) </span></span>  
 <span data-ttu-id="219f0-206">[Base de datos tempdb](tempdb-database.md) </span><span class="sxs-lookup"><span data-stu-id="219f0-206">[tempdb Database](tempdb-database.md) </span></span>  
 <span data-ttu-id="219f0-207">[Base de datos maestra](master-database.md) </span><span class="sxs-lookup"><span data-stu-id="219f0-207">[master Database](master-database.md) </span></span>  
 <span data-ttu-id="219f0-208">[Base de datos msdb](msdb-database.md) </span><span class="sxs-lookup"><span data-stu-id="219f0-208">[msdb Database](msdb-database.md) </span></span>  
 <span data-ttu-id="219f0-209">[Base de datos model](model-database.md) </span><span class="sxs-lookup"><span data-stu-id="219f0-209">[model Database](model-database.md) </span></span>  
 <span data-ttu-id="219f0-210">[Mover bases de datos de usuario](move-user-databases.md) </span><span class="sxs-lookup"><span data-stu-id="219f0-210">[Move User Databases](move-user-databases.md) </span></span>  
 <span data-ttu-id="219f0-211">[Mover archivos de base de datos](move-database-files.md) </span><span class="sxs-lookup"><span data-stu-id="219f0-211">[Move Database Files](move-database-files.md) </span></span>  
 <span data-ttu-id="219f0-212">[Iniciar, detener, pausar, reanudar y reiniciar el motor de base de datos, Agente SQL Server o el Servicio SQL Server Browser](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md) </span><span class="sxs-lookup"><span data-stu-id="219f0-212">[Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md) </span></span>  
 <span data-ttu-id="219f0-213">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="219f0-213">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="219f0-214">Volver a generar bases de datos del sistema</span><span class="sxs-lookup"><span data-stu-id="219f0-214">Rebuild System Databases</span></span>](system-databases.md)  
  
  
