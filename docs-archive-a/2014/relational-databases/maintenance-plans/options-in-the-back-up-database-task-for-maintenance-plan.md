---
title: Tarea Realizar copia de seguridad de la base de datos (Plan de mantenimiento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.backup.f1
- sql12.swb.maint.maintplanproperties.logbackup.f1
helpviewer_keywords:
- Back Up Database Task dialog box
ms.assetid: ed1ef012-fa14-4ba5-bafe-d1527ba065b3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 952730f09deeede360dff5e2bd83f8cdc8a20a67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671517"
---
# <a name="back-up-database-task-maintenance-plan"></a><span data-ttu-id="34e60-102">Tarea Copia de seguridad de base de datos (Plan de mantenimiento)</span><span class="sxs-lookup"><span data-stu-id="34e60-102">Back Up Database Task (Maintenance Plan)</span></span>
  <span data-ttu-id="34e60-103">Utilice el cuadro de diálogo **Tarea Copia de seguridad de la base de datos** para agregar una tarea de copia de seguridad al plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="34e60-103">Use the **Back Up Database Task** dialog to add a backup task to the maintenance plan.</span></span> <span data-ttu-id="34e60-104">Es importante realizar una copia de seguridad de la base de datos por si se produce un error de sistema o del hardware (o un error del usuario) que cause algún tipo de daño en la base de datos y que requiera una copia de seguridad para la restauración.</span><span class="sxs-lookup"><span data-stu-id="34e60-104">Backing up the database is important in case of system or hardware failure (or user errors) that cause the database to be damaged in some way, thus requiring a backed-up copy to be restored.</span></span> <span data-ttu-id="34e60-105">Esta tarea le permite realizar copias de seguridad completas, diferenciales, de archivos y grupos de archivos, así como de registros de transacciones.</span><span class="sxs-lookup"><span data-stu-id="34e60-105">This task allows you to perform full, differential, files and filegroups, and transaction log backups.</span></span>  
  
 <span data-ttu-id="34e60-106">**Para crear una tarea de copia de seguridad de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="34e60-106">**To create a backup database task**</span></span>  
  
-   [<span data-ttu-id="34e60-107">Crear un plan de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="34e60-107">Create a Maintenance Plan</span></span>](create-a-maintenance-plan.md)  
  
## <a name="options"></a><span data-ttu-id="34e60-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="34e60-108">Options</span></span>  
 <span data-ttu-id="34e60-109">**Connection**</span><span class="sxs-lookup"><span data-stu-id="34e60-109">**Connection**</span></span>  
 <span data-ttu-id="34e60-110">Seleccione la conexión al servidor que va a utilizar para la realización de esta tarea.</span><span class="sxs-lookup"><span data-stu-id="34e60-110">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="34e60-111">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="34e60-111">**New**</span></span>  
 <span data-ttu-id="34e60-112">Cree una nueva conexión de servidor que utilizará al realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="34e60-112">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="34e60-113">El cuadro de diálogo **Nueva conexión** se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="34e60-113">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="34e60-114">**Bases de datos**</span><span class="sxs-lookup"><span data-stu-id="34e60-114">**Databases**</span></span>  
 <span data-ttu-id="34e60-115">Especifique las bases de datos a las que afecta esta tarea.</span><span class="sxs-lookup"><span data-stu-id="34e60-115">Specify the databases affected by this task.</span></span> <span data-ttu-id="34e60-116">Cuando se selecciona, la lista desplegable proporciona las siguientes opciones: **Todas las bases de datos**, **Todas las bases de datos del sistema**, **Todas las bases de datos de usuario**, **Estas bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="34e60-116">When selected, the drop down list provides the following options: **All databases**, **All system databases**, **All user databases**, **These specific databases**.</span></span>  
  
 <span data-ttu-id="34e60-117">**Todas las bases de datos**</span><span class="sxs-lookup"><span data-stu-id="34e60-117">**All databases**</span></span>  
 <span data-ttu-id="34e60-118">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34e60-118">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
 <span data-ttu-id="34e60-119">**Todas las bases de datos del sistema (master, msdb y model)**</span><span class="sxs-lookup"><span data-stu-id="34e60-119">**All system databases (master, msdb, model)**</span></span>  
 <span data-ttu-id="34e60-120">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34e60-120">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span> <span data-ttu-id="34e60-121">No se ejecutarán tareas de mantenimiento en las bases de datos creadas por usuarios.</span><span class="sxs-lookup"><span data-stu-id="34e60-121">No maintenance tasks are run against user-created databases.</span></span>  
  
 <span data-ttu-id="34e60-122">**Todas las bases de datos de usuario (master, model y msdb excluidas)**</span><span class="sxs-lookup"><span data-stu-id="34e60-122">**All user databases (excluding master, model, msdb, tempdb)**</span></span>  
 <span data-ttu-id="34e60-123">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos creadas por usuarios.</span><span class="sxs-lookup"><span data-stu-id="34e60-123">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="34e60-124">No se ejecutarán tareas de mantenimiento en las bases de datos del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34e60-124">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
 <span data-ttu-id="34e60-125">**Las bases de datos**</span><span class="sxs-lookup"><span data-stu-id="34e60-125">**These databases**</span></span>  
 <span data-ttu-id="34e60-126">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento únicamente en las bases de datos seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="34e60-126">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="34e60-127">Si elige esta opción, deberá seleccionar al menos una base de datos de la lista.</span><span class="sxs-lookup"><span data-stu-id="34e60-127">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="34e60-128">**Tipo de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="34e60-128">**Backup type**</span></span>  
 <span data-ttu-id="34e60-129">Muestra el tipo de copia de seguridad que se va a realizar.</span><span class="sxs-lookup"><span data-stu-id="34e60-129">Shows the type of backup to be performed.</span></span>  
  
 <span data-ttu-id="34e60-130">**Componente de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="34e60-130">**Backup component**</span></span>  
 <span data-ttu-id="34e60-131">Seleccione **Base de datos** para realizar una copia de seguridad de toda la base de datos.</span><span class="sxs-lookup"><span data-stu-id="34e60-131">Select **Database** to back up the entire database.</span></span> <span data-ttu-id="34e60-132">Seleccione **Archivo y grupos de archivos** para realizar una copia de seguridad únicamente de una parte de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="34e60-132">Select **File and filegroups** to back up only a portion of the database.</span></span> <span data-ttu-id="34e60-133">Si selecciona esta opción, debe especificar el nombre del archivo o del grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="34e60-133">If selected, provide the file or filegroup name.</span></span> <span data-ttu-id="34e60-134">Cuando se seleccionan varias bases de datos en el cuadro **Bases de datos** , solo hay que especificar **Bases de datos** para **Componente de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="34e60-134">When multiple databases are selected in the **Databases** box, only specify **Databases** for the **Backup components**.</span></span> <span data-ttu-id="34e60-135">Para realizar copias de seguridad de un archivo o grupo de archivos, cree una tarea para cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="34e60-135">To perform file or filegroup backups, create a task for each database.</span></span>  
  
 <span data-ttu-id="34e60-136">**El conjunto de copia de seguridad expira**</span><span class="sxs-lookup"><span data-stu-id="34e60-136">**Backup set will expire**</span></span>  
 <span data-ttu-id="34e60-137">Especifica cuándo se puede sobrescribir el conjunto de copia de seguridad con otro conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="34e60-137">Specify when the backup set can be overwritten by another backup set.</span></span>  
  
 <span data-ttu-id="34e60-138">**Copia de seguridad en**</span><span class="sxs-lookup"><span data-stu-id="34e60-138">**Back up to**</span></span>  
 <span data-ttu-id="34e60-139">Realice la copia de seguridad de la base de datos en un archivo o en una cinta.</span><span class="sxs-lookup"><span data-stu-id="34e60-139">Back up the database to a file or to tape.</span></span> <span data-ttu-id="34e60-140">Solo están disponibles los dispositivos de cinta conectados al equipo que contiene la base de datos.</span><span class="sxs-lookup"><span data-stu-id="34e60-140">Only tape devices attached to the computer containing the database are available.</span></span>  
  
 <span data-ttu-id="34e60-141">**Realizar copia de seguridad de las bases de datos en uno o varios archivos**</span><span class="sxs-lookup"><span data-stu-id="34e60-141">**Back up databases across one or more files**</span></span>  
 <span data-ttu-id="34e60-142">Haga clic en **Agregar** para abrir el cuadro de diálogo **Seleccionar destino de la copia de seguridad** y especificar una o varias ubicaciones del disco o dispositivo de cinta.</span><span class="sxs-lookup"><span data-stu-id="34e60-142">Click **Add** to open the **Select Backup Destination** dialog box, and provide one or more a disk location, or tape device.</span></span>  
  
 <span data-ttu-id="34e60-143">**Si existen copias de seguridad**</span><span class="sxs-lookup"><span data-stu-id="34e60-143">**If backup files exist**</span></span>  
 <span data-ttu-id="34e60-144">Seleccione **Anexar** para agregar esta copia de seguridad al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="34e60-144">Select **Append** to add this backup to the end of the file.</span></span> <span data-ttu-id="34e60-145">Seleccione **Sobrescribir**para quitar todas las copias de seguridad antiguas del archivo y reemplazarlas por esta nueva copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="34e60-145">Select **Overwrite**, to remove any old backup in the file and replace them with this new backup.</span></span>  
  
 <span data-ttu-id="34e60-146">**Crear un archivo de copia de seguridad para cada base de datos**</span><span class="sxs-lookup"><span data-stu-id="34e60-146">**Create a backup file for every database**</span></span>  
 <span data-ttu-id="34e60-147">Crea un archivo de copia de seguridad en la ubicación especificada en el cuadro de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="34e60-147">Create a backup file in the location specified in the folder box.</span></span> <span data-ttu-id="34e60-148">Se creará un archivo para cada base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="34e60-148">One file will be created for each database selected.</span></span>  
  
 <span data-ttu-id="34e60-149">**Crear un subdirectorio para cada base de datos**</span><span class="sxs-lookup"><span data-stu-id="34e60-149">**Create a sub-directory for each database**</span></span>  
 <span data-ttu-id="34e60-150">Seleccione esta opción para colocar cada base de datos en una subcarpeta.</span><span class="sxs-lookup"><span data-stu-id="34e60-150">Select to place each database in a subfolder.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="34e60-151">Aunque los planes de mantenimiento pueden crear subdirectorios, las tareas de mantenimiento no pueden eliminar subdirectorios.</span><span class="sxs-lookup"><span data-stu-id="34e60-151">Although maintenance plans can create subdirectories, maintenance tasks cannot delete subdirectories.</span></span> <span data-ttu-id="34e60-152">Esta característica reduce la posibilidad de un ataque malintencionado que utilice la tarea Limpieza de mantenimiento para eliminar archivos.</span><span class="sxs-lookup"><span data-stu-id="34e60-152">This feature reduces the possibility of a malicious attack that uses the Maintenance Cleanup task to delete files.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="34e60-153">El subdirectorio hereda los permisos del directorio principal.</span><span class="sxs-lookup"><span data-stu-id="34e60-153">The subdirectory inherits permissions from the parent directory.</span></span> <span data-ttu-id="34e60-154">Restrinja los permisos para evitar el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="34e60-154">Restrict permissions to avoid unauthorized access.</span></span>  
  
 <span data-ttu-id="34e60-155">**Carpeta**</span><span class="sxs-lookup"><span data-stu-id="34e60-155">**Folder**</span></span>  
 <span data-ttu-id="34e60-156">Especifica la carpeta que va a contener los archivos de base de datos creados de forma automática.</span><span class="sxs-lookup"><span data-stu-id="34e60-156">Specify the folder to contain the automatically created database files.</span></span>  
  
 <span data-ttu-id="34e60-157">**Extensión del archivo de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="34e60-157">**Backup file extension**</span></span>  
 <span data-ttu-id="34e60-158">Especifique la extensión que se va a utilizar para los archivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="34e60-158">Specify the extension to use for the backup files.</span></span> <span data-ttu-id="34e60-159">El valor predeterminado es **.bak**.</span><span class="sxs-lookup"><span data-stu-id="34e60-159">The default is **.bak**.</span></span>  
  
 <span data-ttu-id="34e60-160">**Comprobar integridad de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="34e60-160">**Verify backup integrity**</span></span>  
 <span data-ttu-id="34e60-161">Comprueba que el conjunto de copias de seguridad está completo y que todos los volúmenes son legibles.</span><span class="sxs-lookup"><span data-stu-id="34e60-161">Verify that the backup set is complete and that all volumes are readable.</span></span>  
  
 <span data-ttu-id="34e60-162">**Realizar copia de seguridad del final del registro y dejar la base de datos en estado de restauración**</span><span class="sxs-lookup"><span data-stu-id="34e60-162">**Back up the tail of the log, and leave the database in the restoring state**</span></span>  
 <span data-ttu-id="34e60-163">Realice una copia de seguridad de registros como último paso antes de restaurar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="34e60-163">Perform a log backup as the last step before restoring a database.</span></span> <span data-ttu-id="34e60-164">Para obtener más información, vea [Copias del final del registro &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="34e60-164">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="34e60-165">**Establecer la compresión de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="34e60-165">**Set backup compression**</span></span>  
 <span data-ttu-id="34e60-166">En [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] (o en versiones posteriores), seleccione uno los siguientes valores de [compresión de copia de seguridad](../backup-restore/backup-compression-sql-server.md) :</span><span class="sxs-lookup"><span data-stu-id="34e60-166">In [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] (or a later version), select one the following [backup compression](../backup-restore/backup-compression-sql-server.md) values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34e60-167">**Usar la configuración de servidor predeterminada**</span><span class="sxs-lookup"><span data-stu-id="34e60-167">**Use the default server setting**</span></span>|<span data-ttu-id="34e60-168">Haga clic para utilizar el valor predeterminado de nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="34e60-168">Click to use the server-level default.</span></span><br /><br /> <span data-ttu-id="34e60-169">La opción de la configuración del servidor **Compresión de copia de seguridad predeterminada** establece este valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="34e60-169">This default is set by the **backup compression default** server-configuration option.</span></span> <span data-ttu-id="34e60-170">Para obtener más información sobre cómo ver la configuración actual de esta opción, vea [Ver o establecer la opción de configuración del servidor de compresión de copia de seguridad predeterminada](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="34e60-170">For information about how to view the current setting of this option,  see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>|  
|<span data-ttu-id="34e60-171">**Comprimir copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="34e60-171">**Compress backup**</span></span>|<span data-ttu-id="34e60-172">Haga clic para comprimir la copia de seguridad, sin tener en cuenta el valor predeterminado de nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="34e60-172">Click to compress the backup, regardless of the server-level default.</span></span><br /><br /> <span data-ttu-id="34e60-173">**\*\* Importante \*\*** De forma predeterminada, la compresión aumenta significativamente el uso de CPU y la CPU adicional que consume el proceso de compresión puede afectar negativamente a las operaciones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="34e60-173">**\*\* Important \*\*** By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely affect concurrent operations.</span></span> <span data-ttu-id="34e60-174">Por consiguiente, podría ser conveniente crear copias de seguridad comprimidas de prioridad baja en una sesión en la que el [regulador de recursos](../resource-governor/resource-governor.md)limite el uso de CPU.</span><span class="sxs-lookup"><span data-stu-id="34e60-174">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="34e60-175">Para obtener más información, vea [Usar el regulador de recursos para limitar el uso de CPU mediante compresión de copia de seguridad &#40;Transact-SQL&#41;](../backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)limite el uso de CPU.</span><span class="sxs-lookup"><span data-stu-id="34e60-175">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](../backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>|  
|<span data-ttu-id="34e60-176">**No comprimir copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="34e60-176">**Do not compress backup**</span></span>|<span data-ttu-id="34e60-177">Haga clic para crear una copia de seguridad sin comprimir, independientemente del valor predeterminado de nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="34e60-177">Click to create an uncompressed backup, regardless of the server-level default.</span></span>|  
  
 <span data-ttu-id="34e60-178">**Ver T-SQL**</span><span class="sxs-lookup"><span data-stu-id="34e60-178">**View T-SQL**</span></span>  
 <span data-ttu-id="34e60-179">Muestra las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] realizadas en el servidor para esta tarea, en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="34e60-179">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34e60-180">Si el número de objetos afectados es elevado, es posible que deba esperar un rato hasta que se muestren.</span><span class="sxs-lookup"><span data-stu-id="34e60-180">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="34e60-181">Cuadro de diálogo Nueva conexión</span><span class="sxs-lookup"><span data-stu-id="34e60-181">New Connection Dialog Box</span></span>  
 <span data-ttu-id="34e60-182">**Nombre de la conexión**</span><span class="sxs-lookup"><span data-stu-id="34e60-182">**Connection name**</span></span>  
 <span data-ttu-id="34e60-183">Escriba un nombre para la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="34e60-183">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="34e60-184">**Seleccionar o especificar un nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="34e60-184">**Select or enter a server name**</span></span>  
 <span data-ttu-id="34e60-185">Seleccione un servidor al que conectarse cuando se realice esta tarea.</span><span class="sxs-lookup"><span data-stu-id="34e60-185">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="34e60-186">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="34e60-186">**Refresh**</span></span>  
 <span data-ttu-id="34e60-187">Actualiza la lista de servidores disponibles.</span><span class="sxs-lookup"><span data-stu-id="34e60-187">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="34e60-188">**Especificar información para iniciar sesión en el servidor**</span><span class="sxs-lookup"><span data-stu-id="34e60-188">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="34e60-189">Especifica el modo de autenticación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="34e60-189">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="34e60-190">**Usar seguridad integrada de Windows NT**</span><span class="sxs-lookup"><span data-stu-id="34e60-190">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="34e60-191">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] con autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="34e60-191">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="34e60-192">**Utilizar un nombre de usuario y una contraseña específicos**</span><span class="sxs-lookup"><span data-stu-id="34e60-192">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="34e60-193">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] mediante autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34e60-193">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="34e60-194">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="34e60-194">This option is not available.</span></span>  
  
 <span data-ttu-id="34e60-195">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="34e60-195">**User name**</span></span>  
 <span data-ttu-id="34e60-196">Proporcione un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="34e60-196">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="34e60-197">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="34e60-197">This option is not available.</span></span>  
  
 <span data-ttu-id="34e60-198">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="34e60-198">**Password**</span></span>  
 <span data-ttu-id="34e60-199">Proporcione una contraseña para que se utilice en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="34e60-199">Provide a password to use when authenticating.</span></span> <span data-ttu-id="34e60-200">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="34e60-200">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34e60-201">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34e60-201">See Also</span></span>  
 [<span data-ttu-id="34e60-202">BACKUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="34e60-202">BACKUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-transact-sql)  
  
  
