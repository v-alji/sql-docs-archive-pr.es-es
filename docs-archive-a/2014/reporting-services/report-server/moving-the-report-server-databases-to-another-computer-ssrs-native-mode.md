---
title: Mover las bases de datos del servidor de informes a otro equipo (Modo nativo de SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 44a9854d-e333-44f6-bdc7-8837b9f34416
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 49fd35f57cf783b262b3c690e3047e5f479ab193
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743915"
---
# <a name="moving-the-report-server-databases-to-another-computer-ssrs-native-mode"></a><span data-ttu-id="52ea7-102">Mover las bases de datos del servidor de informes a otro equipo (Modo nativo de SSRS)</span><span class="sxs-lookup"><span data-stu-id="52ea7-102">Moving the Report Server Databases to Another Computer (SSRS Native Mode)</span></span>
  <span data-ttu-id="52ea7-103">Puede trasladar las bases de datos del servidor de informes que se usan en una instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] a una instancia de que se encuentre en un equipo diferente.</span><span class="sxs-lookup"><span data-stu-id="52ea7-103">You can move the report server databases that are used in an installation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] to an instance that is on a different computer.</span></span> <span data-ttu-id="52ea7-104">Las bases de datos reportserver y reportservertempdb se deben mover o copiar en conjunto.</span><span class="sxs-lookup"><span data-stu-id="52ea7-104">Both the reportserver and reportservertempdb databases must be moved or copied together.</span></span> <span data-ttu-id="52ea7-105">Una instalación de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] requiere las dos bases de datos; la base de datos reportservertempdb debe estar relacionada por nombre con la base de datos reportserver principal que se vaya a mover.</span><span class="sxs-lookup"><span data-stu-id="52ea7-105">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation requires both databases; the reportservertempdb database must be related by name to the primary reportserver database you are moving.</span></span>  
  
 <span data-ttu-id="52ea7-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo.</span><span class="sxs-lookup"><span data-stu-id="52ea7-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>  
  
 <span data-ttu-id="52ea7-107">Mover una base de datos no afecta a las operaciones programadas que están actualmente definidas para los elementos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="52ea7-107">Moving a database does not effect scheduled operations that are currently defined for report server items.</span></span>  
  
-   <span data-ttu-id="52ea7-108">Las programaciones se volverán a crear la primera vez que se reinicie el servicio del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="52ea7-108">Schedules will be recreated the first time that you restart the Report Server service.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="52ea7-109">Los trabajos de agente que se utilizan para activar una programación se volverán a crear en la nueva instancia de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="52ea7-109">Agent jobs that are used to trigger a schedule will be recreated on the new database instance.</span></span> <span data-ttu-id="52ea7-110">No tiene que mover los trabajos al nuevo equipo, pero quizá desee eliminar los trabajos del equipo que ya no se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="52ea7-110">You do not have to move the jobs to the new computer, but you might want to delete jobs on the computer that will no longer be used.</span></span>  
  
-   <span data-ttu-id="52ea7-111">Las suscripciones, los informes almacenados en caché y las instantáneas se mantienen en la base de datos que se ha movido.</span><span class="sxs-lookup"><span data-stu-id="52ea7-111">Subscriptions, cached reports, and snapshots are preserved in the moved database.</span></span> <span data-ttu-id="52ea7-112">Si una instantánea no está recopilando los datos actualizados después de que se mueve la base de datos, borre las opciones de instantánea en Administrador de informes, haga clic en **Aplicar** para guardar los cambios, vuelva a crear la programación y haga clic en **Aplicar** de nuevo para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="52ea7-112">If a snapshot is not picking up refreshed data after the database is moved, clear the snapshot options in Report Manager, click **Apply** to save your changes, re-create the schedule, and click **Apply** again to save your changes.</span></span>  
  
-   <span data-ttu-id="52ea7-113">Los datos temporales de informes y de sesión de usuario que se almacenan en reportservertempdb permanecen al mover esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="52ea7-113">Temporary report and user session data that is stored in reportservertempdb are persisted when you move that database.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="52ea7-114">proporciona varios métodos para mover bases de datos, como las operaciones de copia de seguridad y restauración, adjuntar y separar, y copiar.</span><span class="sxs-lookup"><span data-stu-id="52ea7-114">provides several approaches for moving databases, including backup and restore, attach and detach, and copy.</span></span> <span data-ttu-id="52ea7-115">No todos los métodos son adecuados para reubicar una base de datos existente en una instancia de servidor nueva.</span><span class="sxs-lookup"><span data-stu-id="52ea7-115">Not all approaches are appropriate for relocating an existing database to a new server instance.</span></span> <span data-ttu-id="52ea7-116">El método recomendado para mover una base de datos del servidor de informes varía en función de sus requisitos de disponibilidad del sistema.</span><span class="sxs-lookup"><span data-stu-id="52ea7-116">The approach that you should use to move the report server database will vary depending on your system availability requirements.</span></span> <span data-ttu-id="52ea7-117">La manera más sencilla de mover bases de datos del servidor de informes es adjuntarlas y separarlas.</span><span class="sxs-lookup"><span data-stu-id="52ea7-117">The easiest way to move the report server databases is to attach and detach them.</span></span> <span data-ttu-id="52ea7-118">Sin embargo, este método requiere que el servidor de informes esté sin conexión mientras se separa la base de datos.</span><span class="sxs-lookup"><span data-stu-id="52ea7-118">However, this approach requires that you take the report server offline while you detach the database.</span></span> <span data-ttu-id="52ea7-119">Las operaciones de copia de seguridad y restauración son la opción más adecuada si se desean reducir al mínimo las interrupciones del servicio, pero deberán ejecutarse comandos [!INCLUDE[tsql](../../includes/tsql-md.md)] para realizarlas.</span><span class="sxs-lookup"><span data-stu-id="52ea7-119">Backup and restore is a better choice if you want to minimize service disruptions, but you must run [!INCLUDE[tsql](../../includes/tsql-md.md)] commands to perform the operations.</span></span> <span data-ttu-id="52ea7-120">No se recomienda copiar la base de datos, en especial mediante el Asistente para copiar bases de datos, ya que no se conserva la configuración de permisos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="52ea7-120">Copying the database is not recommended (specifically, by using the Copy Database Wizard); it does not preserve permission settings in the database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="52ea7-121">Los pasos que se proporcionan en este tema se recomiendan cuando la modificación de la ubicación de la base de datos del servidor de informes es el único cambio que se realiza en la instalación existente.</span><span class="sxs-lookup"><span data-stu-id="52ea7-121">The steps provided in this topic are recommended when relocating the report server database is the only change you are making to the existing installation.</span></span> <span data-ttu-id="52ea7-122">Para migrar una instalación completa de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (es decir, mover la base de datos y cambiar la identidad del servicio Windows del servidor de informes que usa la base de datos), es necesario volver a configurar la conexión y restablecer una clave de cifrado.</span><span class="sxs-lookup"><span data-stu-id="52ea7-122">Migrating an entire [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation (that is, moving the database and changing the identity of the Report Server Windows service that uses the database) requires connection reconfiguration and an encryption key reset.</span></span>  
  
## <a name="detaching-and-attaching-the-report-server-databases"></a><span data-ttu-id="52ea7-123">Separar y adjuntar bases de datos del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="52ea7-123">Detaching and Attaching the Report Server Databases</span></span>  
 <span data-ttu-id="52ea7-124">Si puede poner el servidor de informes sin conexión, puede separar las bases de datos para moverlas a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que desea usar.</span><span class="sxs-lookup"><span data-stu-id="52ea7-124">If you can take the report server offline, you can detach the databases to move them to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to use.</span></span> <span data-ttu-id="52ea7-125">Con este método, se conservan los permisos de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="52ea7-125">This approach preserves permissions in the databases.</span></span> <span data-ttu-id="52ea7-126">Si utiliza una base de datos de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , debe moverla a otra instancia de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52ea7-126">If you are using a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] database, you must move it to another [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instance.</span></span> <span data-ttu-id="52ea7-127">Después de mover las bases de datos, será necesario volver a configurar la conexión del servidor de informes con la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="52ea7-127">After you move the databases, you must reconfigure the report server connection to the report server database.</span></span> <span data-ttu-id="52ea7-128">Si se utiliza una implementación escalada, será necesario volver a configurar la conexión de la base de datos del servidor de informes para cada servidor de informes de la implementación.</span><span class="sxs-lookup"><span data-stu-id="52ea7-128">If you are running a scale-out deployment, you must reconfigure the report server database connection for each report server in the deployment.</span></span>  
  
 <span data-ttu-id="52ea7-129">Lleve a cabo los siguientes pasos para mover las bases de datos:</span><span class="sxs-lookup"><span data-stu-id="52ea7-129">Use the following steps to move the databases:</span></span>  
  
1.  <span data-ttu-id="52ea7-130">Haga una copia de seguridad de las claves de cifrado para la base de datos del servidor de informes que desea mover.</span><span class="sxs-lookup"><span data-stu-id="52ea7-130">Backup the encryption keys for the report server database you want to move.</span></span> <span data-ttu-id="52ea7-131">Puede utilizar la herramienta de configuración [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para hacer una copia de seguridad de las claves.</span><span class="sxs-lookup"><span data-stu-id="52ea7-131">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool backup the keys.</span></span>  
  
2.  <span data-ttu-id="52ea7-132">Detenga el servicio del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="52ea7-132">Stop the Report Server service.</span></span> <span data-ttu-id="52ea7-133">Puede utilizar la herramienta de configuración [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="52ea7-133">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to stop the service.</span></span>  
  
3.  <span data-ttu-id="52ea7-134">Inicie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] y abra una conexión a la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instancia de que hospeda las bases de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="52ea7-134">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and open a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that hosts the report server databases.</span></span>  
  
4.  <span data-ttu-id="52ea7-135">Haga clic con el botón derecho en la base de datos del servidor de informes, seleccione Tareas y haga clic en **Separar**.</span><span class="sxs-lookup"><span data-stu-id="52ea7-135">Right-click the report server database, point to Tasks, and click **Detach**.</span></span> <span data-ttu-id="52ea7-136">Repita este paso para la base de datos temporal del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="52ea7-136">Repeat this step for the report server temporary database.</span></span>  
  
5.  <span data-ttu-id="52ea7-137">Copie o mueva los archivos .mdf y .ldf a la carpeta de datos de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="52ea7-137">Copy or move the .mdf and .ldf files to the Data folder of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to use.</span></span> <span data-ttu-id="52ea7-138">Dado que se van a mover dos bases de datos, asegúrese de que mueve o copia los cuatro archivos.</span><span class="sxs-lookup"><span data-stu-id="52ea7-138">Because you are moving two databases, make sure that you move or copy all four files.</span></span>  
  
6.  <span data-ttu-id="52ea7-139">En [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], abra una conexión con la nueva instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que alojará las bases de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="52ea7-139">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a connection to the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that will host the report server databases.</span></span>  
  
7.  <span data-ttu-id="52ea7-140">Haga clic con el botón derecho en el nodo Bases de datos y luego haga clic en **Adjuntar**.</span><span class="sxs-lookup"><span data-stu-id="52ea7-140">Right-click the Databases node, and then click **Attach**.</span></span>  
  
8.  <span data-ttu-id="52ea7-141">Haga clic en **Agregar** para seleccionar los archivos .mdf y .ldf de la base de datos del servidor de informes que desea adjuntar.</span><span class="sxs-lookup"><span data-stu-id="52ea7-141">Click **Add** to select the report server database .mdf and .ldf files that you want to attach.</span></span> <span data-ttu-id="52ea7-142">Repita este paso para la base de datos temporal del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="52ea7-142">Repeat this step for the report server temporary database.</span></span>  
  
9. <span data-ttu-id="52ea7-143">Una vez asociadas las bases de datos, compruebe que `RSExecRole` es un rol de base de datos en la base de datos del servidor de informes y en la base de datos temporal.</span><span class="sxs-lookup"><span data-stu-id="52ea7-143">After the databases are attached, verify that the `RSExecRole` is a database role in the report server database and temporary database.</span></span> <span data-ttu-id="52ea7-144">`RSExecRole`debe tener permisos Select, INSERT, Update, delete y Reference en las tablas de base de datos del servidor de informes y permisos Execute en los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="52ea7-144">`RSExecRole` must have select, insert, update, delete, and reference permissions on the report server database tables, and execute permissions on the stored procedures.</span></span> <span data-ttu-id="52ea7-145">Para obtener más información, vea [Crear el RSExecRole](../security/create-the-rsexecrole.md).</span><span class="sxs-lookup"><span data-stu-id="52ea7-145">For more information, see [Create the RSExecRole](../security/create-the-rsexecrole.md).</span></span>  
  
10. <span data-ttu-id="52ea7-146">Inicie la herramienta de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y abra una conexión con el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="52ea7-146">Start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool and open a connection to the report server.</span></span>  
  
11. <span data-ttu-id="52ea7-147">En la página Base de datos, seleccione la nueva instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="52ea7-147">On the Database page, select the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, and then click **Connect**.</span></span>  
  
12. <span data-ttu-id="52ea7-148">Seleccione la base de datos del servidor de informes que acaba de mover y haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="52ea7-148">Select the report server database that you just moved, and then click **Apply**.</span></span>  
  
13. <span data-ttu-id="52ea7-149">En la página Claves de cifrado, haga clic en Restaurar.</span><span class="sxs-lookup"><span data-stu-id="52ea7-149">On the Encryption Keys page, click Restore.</span></span> <span data-ttu-id="52ea7-150">Especifique el archivo que contiene la copia de seguridad de las claves y la contraseña para desbloquear el archivo.</span><span class="sxs-lookup"><span data-stu-id="52ea7-150">Specify the file that contains the backup copy of the keys and the password to unlock the file.</span></span>  
  
14. <span data-ttu-id="52ea7-151">Reinicie el servicio del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="52ea7-151">Restart the Report Server service.</span></span>  
  
## <a name="backing-up-and-restoring-the-report-server-databases"></a><span data-ttu-id="52ea7-152">Realizar copias de seguridad de las bases de datos del servidor de informes y restaurarlas</span><span class="sxs-lookup"><span data-stu-id="52ea7-152">Backing Up and Restoring the Report Server Databases</span></span>  
 <span data-ttu-id="52ea7-153">Si no es posible que el servidor de informes esté sin conexión, puede realizar una copia de seguridad de las bases de datos del servidor de informes y restaurarlas para cambiar su ubicación.</span><span class="sxs-lookup"><span data-stu-id="52ea7-153">If you cannot take the report server offline, you can use backup and restore to relocate the report server databases.</span></span> <span data-ttu-id="52ea7-154">Debe usar instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] para realizar copias de seguridad y restauraciones.</span><span class="sxs-lookup"><span data-stu-id="52ea7-154">You must use [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to do the backup and restore.</span></span> <span data-ttu-id="52ea7-155">Después de restaurar las bases de datos, debe configurar el servidor de informes para que utilice la base de datos en la nueva instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="52ea7-155">After you restore the databases, you must configure the report server to use the database on the new server instance.</span></span> <span data-ttu-id="52ea7-156">Para obtener más información, vea las instrucciones que se incluyen al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="52ea7-156">For more information, see the instructions at the end of this topic.</span></span>  
  
### <a name="using-backup-and-copy_only-to-backup-the-report-server-databases"></a><span data-ttu-id="52ea7-157">Usar BACKUP y COPY_ONLY para la copia de seguridad de las bases de datos del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="52ea7-157">Using BACKUP and COPY_ONLY to Backup the Report Server Databases</span></span>  
 <span data-ttu-id="52ea7-158">Cuando realice copias de seguridad de las bases de datos, establezca el argumento COPY_ONLY.</span><span class="sxs-lookup"><span data-stu-id="52ea7-158">When backing up the databases, set the COPY_ONLY argument.</span></span> <span data-ttu-id="52ea7-159">Asegúrese de incluir ambas bases de datos y los archivos de registro en la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="52ea7-159">Be sure to back up both of the databases and log files.</span></span>  
  
```  
-- To permit log backups, before the full database backup, alter the database   
-- to use the full recovery model.  
USE master;  
GO  
ALTER DATABASE ReportServer  
   SET RECOVERY FULL  
  
-- If the ReportServerData device does not exist yet, create it.   
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerData',   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\BACKUP\ReportServerData.bak'  
  
-- Create a logical backup device, ReportServerLog.  
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerLog',   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\BACKUP\ReportServerLog.bak'  
  
-- Back up the full ReportServer database.  
BACKUP DATABASE ReportServer  
   TO ReportServerData  
   WITH COPY_ONLY  
  
-- Back up the ReportServer log.  
BACKUP LOG ReportServer  
   TO ReportServerLog  
   WITH COPY_ONLY  
  
-- To permit log backups, before the full database backup, alter the database   
-- to use the full recovery model.  
USE master;  
GO  
ALTER DATABASE ReportServerTempdb  
   SET RECOVERY FULL  
  
-- If the ReportServerTempDBData device does not exist yet, create it.   
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerTempDBData',   
'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\BACKUP\ReportServerTempDBData.bak'  
  
-- Create a logical backup device, ReportServerTempDBLog.  
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerTempDBLog',   
'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\BACKUP\ReportServerTempDBLog.bak'  
  
-- Back up the full ReportServerTempDB database.  
BACKUP DATABASE ReportServerTempDB  
   TO ReportServerTempDBData  
   WITH COPY_ONLY  
  
-- Back up the ReportServerTempDB log.  
BACKUP LOG ReportServerTempDB  
   TO ReportServerTempDBLog  
   WITH COPY_ONLY  
```  
  
### <a name="using-restore-and-move-to-relocate-the-report-server-databases"></a><span data-ttu-id="52ea7-160">Usar RESTORE y MOVE para cambiar la ubicación de las bases de datos del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="52ea7-160">Using RESTORE and MOVE to Relocate the Report Server Databases</span></span>  
 <span data-ttu-id="52ea7-161">Al restaurar las bases de datos, no olvide incluir el argumento MOVE para especificar una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="52ea7-161">When restoring the databases, be sure to include the MOVE argument so that you can specify a path.</span></span> <span data-ttu-id="52ea7-162">Use el argumento NORECOVERY para realizar la restauración inicial; de esta manera, la base de datos se mantendrá en estado RESTORING y tendrá tiempo para revisar las copias de seguridad de los registros y determinar cuál desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="52ea7-162">Use the NORECOVERY argument to perform the initial restore; this keeps the database in a RESTORING state, giving you time to review log backups to determine which one to restore.</span></span> <span data-ttu-id="52ea7-163">En el último paso se repite la operación RESTORE con el argumento RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="52ea7-163">The final step repeats the RESTORE operation with the RECOVERY argument.</span></span>  
  
 <span data-ttu-id="52ea7-164">El argumento MOVE utiliza el nombre lógico del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="52ea7-164">The MOVE argument uses the logical name of the data file.</span></span> <span data-ttu-id="52ea7-165">Para encontrar el nombre lógico, ejecute la siguiente instrucción: `RESTORE FILELISTONLY FROM DISK='C:\ReportServerData.bak';`</span><span class="sxs-lookup"><span data-stu-id="52ea7-165">To find the logical name, execute the following statement: `RESTORE FILELISTONLY FROM DISK='C:\ReportServerData.bak';`</span></span>  
  
 <span data-ttu-id="52ea7-166">En los ejemplos siguientes se incluye el argumento FILE para poder especificar la posición del archivo de registro que se desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="52ea7-166">The following examples include the FILE argument so that you can specify the file position of the log file to restore.</span></span> <span data-ttu-id="52ea7-167">Para encontrar la posición del archivo, ejecute la siguiente instrucción: `RESTORE HEADERONLY FROM DISK='C:\ReportServerData.bak';`</span><span class="sxs-lookup"><span data-stu-id="52ea7-167">To find the file position, execute the following statement: `RESTORE HEADERONLY FROM DISK='C:\ReportServerData.bak';`</span></span>  
  
 <span data-ttu-id="52ea7-168">Al restaurar la base de datos y los archivos de registro, cada operación RESTORE se debe ejecutar por separado.</span><span class="sxs-lookup"><span data-stu-id="52ea7-168">When restoring the database and log files, you should run each RESTORE operation separately.</span></span>  
  
```  
-- Restore the report server database and move to new instance folder   
RESTORE DATABASE ReportServer  
   FROM DISK='C:\ReportServerData.bak'  
   WITH NORECOVERY,   
      MOVE 'ReportServer' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer.mdf',   
      MOVE 'ReportServer_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer_Log.ldf';  
GO  
  
-- Restore the report server log file to new instance folder   
RESTORE LOG ReportServer  
   FROM DISK='C:\ReportServerData.bak'  
   WITH NORECOVERY, FILE=2  
      MOVE 'ReportServer' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer.mdf',   
      MOVE 'ReportServer_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer_Log.ldf';  
GO  
  
-- Restore and move the report server temporary database  
RESTORE DATABASE ReportServerTempdb  
   FROM DISK='C:\ReportServerTempDBData.bak'  
   WITH NORECOVERY,   
      MOVE 'ReportServerTempDB' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServerTempDB.mdf',   
      MOVE 'ReportServerTempDB_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\REportServerTempDB_Log.ldf';  
GO  
  
-- Restore the temporary database log file to new instance folder   
RESTORE LOG ReportServerTempdb  
   FROM DISK='C:\ReportServerTempDBData.bak'  
   WITH NORECOVERY, FILE=2  
      MOVE 'ReportServerTempDB' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServerTempDB.mdf',   
      MOVE 'ReportServerTempDB_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\REportServerTempDB_Log.ldf';  
GO  
  
-- Perform final restore  
RESTORE DATABASE ReportServer  
   WITH RECOVERY  
GO  
  
-- Perform final restore  
RESTORE DATABASE ReportServerTempDB  
   WITH RECOVERY  
GO  
```  
  
### <a name="how-to-configure-the-report-server-database-connection"></a><span data-ttu-id="52ea7-169">Configurar la conexión de la base de datos del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="52ea7-169">How to Configure the Report Server Database Connection</span></span>  
  
1.  <span data-ttu-id="52ea7-170">Inicie el Administrador de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y abra una conexión con el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="52ea7-170">Start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager and open a connection to the report server.</span></span>  
  
2.  <span data-ttu-id="52ea7-171">En la página Base de datos, haga clic en **Cambiar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="52ea7-171">On the Database page, click **Change Database**.</span></span> <span data-ttu-id="52ea7-172">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="52ea7-172">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="52ea7-173">Haga clic en **Elija una base de datos del servidor de informes existente**.</span><span class="sxs-lookup"><span data-stu-id="52ea7-173">Click **Choose an existing report server database**.</span></span> <span data-ttu-id="52ea7-174">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="52ea7-174">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="52ea7-175">Seleccione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que ahora aloja la base de datos del servidor de informes y haga clic en **Probar conexión**.</span><span class="sxs-lookup"><span data-stu-id="52ea7-175">Select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that now hosts the report server database and click **Test Connection**.</span></span> <span data-ttu-id="52ea7-176">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="52ea7-176">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="52ea7-177">En Nombre de la base de datos, seleccione la base de datos del servidor de informes que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="52ea7-177">In Database Name, select the report server database that you want to use.</span></span> <span data-ttu-id="52ea7-178">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="52ea7-178">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="52ea7-179">En Credenciales, especifique las credenciales que utilizará el servidor de informes para conectarse a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="52ea7-179">In Credentials, specify the credentials that the report server will use to connect to the report server database.</span></span> <span data-ttu-id="52ea7-180">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="52ea7-180">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="52ea7-181">Haga clic en **Siguiente** y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="52ea7-181">Click **Next** and then **Finish**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52ea7-182">Una instalación [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] requiere que la instancia [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] incluya el rol `RSExecRole`.</span><span class="sxs-lookup"><span data-stu-id="52ea7-182">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation requires that the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance include the `RSExecRole` role.</span></span> <span data-ttu-id="52ea7-183">La creación de roles, el registro de inicio de sesión y las asignaciones de roles tienen lugar cuando se establece la conexión de la base de datos del servidor de informes a través de la herramienta de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52ea7-183">Role creation, login registration, and role assignments occur when you set the report server database connection through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span> <span data-ttu-id="52ea7-184">Si se utilizan métodos alternativos (concretamente, si se utiliza la herramienta del símbolo del sistema rsconfig.exe) para configurar la conexión, el servidor de informes no estará en estado de funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="52ea7-184">If you use alternate approaches (specifically, if you use the rsconfig.exe command prompt utility) to configure the connection, the report server will not be in a working state.</span></span> <span data-ttu-id="52ea7-185">Es posible que tenga que escribir código WMI para que el servidor de informes esté disponible.</span><span class="sxs-lookup"><span data-stu-id="52ea7-185">You might have to write WMI code to make the report server available.</span></span> <span data-ttu-id="52ea7-186">Para obtener más información, vea [Obtener acceso al proveedor WMI de Reporting Services](../tools/access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="52ea7-186">For more information, see [Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52ea7-187">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52ea7-187">See Also</span></span>  
 <span data-ttu-id="52ea7-188">[Crear RSExecRole](../security/create-the-rsexecrole.md) </span><span class="sxs-lookup"><span data-stu-id="52ea7-188">[Create the RSExecRole](../security/create-the-rsexecrole.md) </span></span>  
 <span data-ttu-id="52ea7-189">[Iniciar y detener el servicio del servidor de informes](start-and-stop-the-report-server-service.md) </span><span class="sxs-lookup"><span data-stu-id="52ea7-189">[Start and Stop the Report Server Service](start-and-stop-the-report-server-service.md) </span></span>  
 <span data-ttu-id="52ea7-190">[Configurar una conexión a la base de datos del servidor de informes &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="52ea7-190">[Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="52ea7-191">[Configure la cuenta de ejecución desatendida &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="52ea7-191">[Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="52ea7-192">[Administrador de configuración de Reporting Services &#40;modo nativo&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="52ea7-192">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="52ea7-193">[Utilidad rsconfig &#40;SSRS&#41;](../tools/rsconfig-utility-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="52ea7-193">[rsconfig Utility &#40;SSRS&#41;](../tools/rsconfig-utility-ssrs.md) </span></span>  
 <span data-ttu-id="52ea7-194">[Configurar y administrar claves de cifrado &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) </span><span class="sxs-lookup"><span data-stu-id="52ea7-194">[Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) </span></span>  
 [<span data-ttu-id="52ea7-195">Base de datos del servidor de informes &#40;Modo nativo de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="52ea7-195">Report Server Database &#40;SSRS Native Mode&#41;</span></span>](report-server-database-ssrs-native-mode.md)  
  
  
