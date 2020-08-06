---
title: Creación de una copia de seguridad completa de base de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [SQL Server], full backups
- backing up databases [SQL Server], SQL Server Management Studio
- backups [SQL Server], creating
- database backups [SQL Server], SQL Server Management Studio
ms.assetid: 586561fc-dfbb-4842-84f8-204a9100a534
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f406464680a1669133dc87bdfb231c644d33fbdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749994"
---
# <a name="create-a-full-database-backup-sql-server"></a><span data-ttu-id="2035f-102">Crear una copia de seguridad completa de base de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2035f-102">Create a Full Database Backup (SQL Server)</span></span>
  <span data-ttu-id="2035f-103">En este tema se describe cómo crear una copia de seguridad completa de la base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2035f-103">This topic describes how to create a full database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2035f-104">Para obtener información sobre SQL Server copia de seguridad en el servicio de almacenamiento de blobs de Azure, consulte [SQL Server Backup and restore with Azure BLOB Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="2035f-104">For information on SQL Server backup to the Azure Blob storage service, see, [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="2035f-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="2035f-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2035f-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="2035f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2035f-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="2035f-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2035f-108">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="2035f-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="2035f-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2035f-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2035f-110">**Para crear una copia de seguridad completa de la base de datos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="2035f-110">**To create a full database backup, using:**</span></span>  
  
     [<span data-ttu-id="2035f-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2035f-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2035f-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2035f-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="2035f-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="2035f-113">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="2035f-114">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="2035f-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2035f-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="2035f-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2035f-116">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="2035f-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2035f-117">La instrucción BACKUP no se permite en una transacción explícita o implícita.</span><span class="sxs-lookup"><span data-stu-id="2035f-117">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="2035f-118">Las copias de seguridad que se crean en una versión más reciente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se pueden restaurar en versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2035f-118">Backups that are created by more recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be restored in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="2035f-119">Para obtener más información, vea [Información general de copia de seguridad &#40;SQL Server&#41;](backup-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2035f-119">For more information, see [Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="2035f-120">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="2035f-120">Recommendations</span></span>  
  
-   <span data-ttu-id="2035f-121">A medida que la base de datos aumenta de tamaño, las copias de seguridad completas requieren una mayor cantidad de tiempo para finalizar y espacio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="2035f-121">As a database increases in size full database backups take more time to finish and require more storage space.</span></span> <span data-ttu-id="2035f-122">Por ello, para una base de datos grande, puede que desee complementar una copia de seguridad completa con una serie de *copias de seguridad diferenciales*.</span><span class="sxs-lookup"><span data-stu-id="2035f-122">Therefore, for a large database, you might want to supplement a full database backup with a series of *differential database backups*.</span></span> <span data-ttu-id="2035f-123">Para obtener más información, vea [Copias de seguridad diferenciales &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2035f-123">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="2035f-124">Para calcular el tamaño de la copia de seguridad completa de la base de datos, use el procedimiento almacenado del sistema [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="2035f-124">You can estimate the size of a full database backup by using the [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) system stored procedure.</span></span>  
  
-   <span data-ttu-id="2035f-125">De forma predeterminada, cada operación de copia de seguridad correcta agrega una entrada en el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y en el registro de eventos del sistema.</span><span class="sxs-lookup"><span data-stu-id="2035f-125">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="2035f-126">Si hace una copia de seguridad del registro de transacciones con frecuencia, estos mensajes que indican la corrección de la operación pueden acumularse rápidamente, con lo que se crean registros de errores muy grandes que pueden dificultar la búsqueda de otros mensajes.</span><span class="sxs-lookup"><span data-stu-id="2035f-126">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="2035f-127">En esos casos, puede suprimir estas entradas de registro utilizando la marca de seguimiento 3226 si ninguno de los scripts depende de esas entradas.</span><span class="sxs-lookup"><span data-stu-id="2035f-127">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="2035f-128">Para obtener más información, vea [Marcas de seguimiento &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2035f-128">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2035f-129">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2035f-129">Security</span></span>  
 <span data-ttu-id="2035f-130">TRUSTWORTHY se establece en OFF en una copia de seguridad de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2035f-130">TRUSTWORTHY is set to OFF on a database backup.</span></span> <span data-ttu-id="2035f-131">Para obtener información sobre cómo establecer TRUSTWORTHY en ON, vea [Opciones de ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="2035f-131">For information about how to set TRUSTWORTHY to ON, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="2035f-132">A partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] las opciones `PASSWORD` y `MEDIAPASSWORD` se suspenden para crear copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2035f-132">Beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] the `PASSWORD` and `MEDIAPASSWORD` options are discontinued for creating backups.</span></span> <span data-ttu-id="2035f-133">Todavía puede restaurar las copias de seguridad creadas con contraseñas.</span><span class="sxs-lookup"><span data-stu-id="2035f-133">You can still restore backups created with passwords.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2035f-134">Permisos</span><span class="sxs-lookup"><span data-stu-id="2035f-134">Permissions</span></span>  
 <span data-ttu-id="2035f-135">De forma predeterminada, los permisos BACKUP DATABASE y BACKUP LOG corresponden a los miembros del rol fijo de servidor **sysadmin** y de los roles fijos de base de datos **db_owner** y **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="2035f-135">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="2035f-136">Los problemas de propiedad y permisos del archivo físico del dispositivo de copia de seguridad pueden interferir con una operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2035f-136">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2035f-137">debe poder leer y escribir en el dispositivo y la cuenta en la que se ejecuta el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe tener permisos de escritura.</span><span class="sxs-lookup"><span data-stu-id="2035f-137">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="2035f-138">En cambio, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que agrega una entrada para un dispositivo de copia de seguridad en las tablas del sistema, no comprueba los permisos de acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="2035f-138">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="2035f-139">Es posible que estos problemas con el archivo físico del dispositivo de copia de seguridad no aparezcan hasta que se tenga acceso al recurso físico, al intentar la copia de seguridad o la restauración.</span><span class="sxs-lookup"><span data-stu-id="2035f-139">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2035f-140">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2035f-140">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2035f-141">Al especificar una tarea de copia de seguridad mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], puede generar el script [!INCLUDE[tsql](../../includes/tsql-md.md)] [BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and selecting a script destination.</span><span class="sxs-lookup"><span data-stu-id="2035f-141">When you specify a back up task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)] [BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and selecting a script destination.</span></span>  
  
#### <a name="to-back-up-a-database"></a><span data-ttu-id="2035f-142">Para realizar una copia de seguridad de una base de datos</span><span class="sxs-lookup"><span data-stu-id="2035f-142">To back up a database</span></span>  
  
1.  <span data-ttu-id="2035f-143">Después de conectarse a la instancia apropiada de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2035f-143">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="2035f-144">Expanda **Bases de datos**y, dependiendo de la base de datos, seleccione una base de datos de usuario o expanda **Bases de datos del sistema** y seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="2035f-144">Expand **Databases**, and depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="2035f-145">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y haga clic en **Copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="2035f-145">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="2035f-146">Aparece el cuadro de diálogo **Copia de seguridad de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="2035f-146">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="2035f-147">En el `Database` cuadro de lista, compruebe el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2035f-147">In the `Database` list box, verify the database name.</span></span> <span data-ttu-id="2035f-148">También puede seleccionar otra base de datos en la lista.</span><span class="sxs-lookup"><span data-stu-id="2035f-148">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="2035f-149">Puede realizar una copia de seguridad de la base de datos en cualquier modelo de recuperación (**FULL**, **BULK_LOGGED**o **SIMPLE**).</span><span class="sxs-lookup"><span data-stu-id="2035f-149">You can perform a database backup for any recovery model (**FULL**, **BULK_LOGGED**, or **SIMPLE**).</span></span>  
  
6.  <span data-ttu-id="2035f-150">En el cuadro de lista **Tipo de copia de seguridad**, seleccione **Completa**.</span><span class="sxs-lookup"><span data-stu-id="2035f-150">In the **Backup type** list box, select **Full**.</span></span>  
  
     <span data-ttu-id="2035f-151">Tenga en cuenta que después de crear una copia de seguridad completa de la base de datos, puede crear una copia de seguridad diferencial; para obtener más información, vea [Crear una copia de seguridad diferencial de una base de datos &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2035f-151">Note that after creating a full database backup, you can create a differential database backup; for more information, see [Create a Differential Database Backup &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md).</span></span>  
  
7.  <span data-ttu-id="2035f-152">También puede seleccionar **Copia de seguridad de solo copia** para crear un copia de seguridad de solo copia.</span><span class="sxs-lookup"><span data-stu-id="2035f-152">Optionally, you can select **Copy Only Backup** to create a copy-only backup.</span></span> <span data-ttu-id="2035f-153">Una *copia de seguridad de solo copia* es una copia de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] independiente de la secuencia de copias de seguridad convencionales de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2035f-153">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="2035f-154">Para obtener más información, vea [Copias de seguridad de solo copia &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2035f-154">For more information, see [Copy-Only Backups &#40;SQL Server&#41;](copy-only-backups-sql-server.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2035f-155">Cuando la opción **Diferencial** está seleccionada, no puede crear una copia de seguridad de solo copia.</span><span class="sxs-lookup"><span data-stu-id="2035f-155">When the **Differential** option is selected, you cannot create a copy-only backup.</span></span>  
  
8.  <span data-ttu-id="2035f-156">En **componente de copia de seguridad**, haga clic en `Database` .</span><span class="sxs-lookup"><span data-stu-id="2035f-156">For **Backup component**, click `Database`.</span></span>  
  
9. <span data-ttu-id="2035f-157">Acepte el nombre del conjunto de copia de seguridad predeterminado sugerido en el cuadro de texto **Nombre** o especifique otro nombre.</span><span class="sxs-lookup"><span data-stu-id="2035f-157">Either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
10. <span data-ttu-id="2035f-158">Opcionalmente, en el cuadro de texto **Descripción** , escriba una descripción del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2035f-158">Optionally, in the **Description** text box, enter a description of the backup set.</span></span>  
  
11. <span data-ttu-id="2035f-159">Elija el tipo de destino de la copia de seguridad haciendo clic en **Disco**, **Cinta** o **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="2035f-159">Choose the type of backup destination by clicking **Disk**, **Tape** or **URL**.</span></span> <span data-ttu-id="2035f-160">Para seleccionar las rutas de acceso de hasta 64 unidades de disco o cinta que contienen un solo conjunto de medios, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2035f-160">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="2035f-161">Las rutas seleccionadas se muestran en el cuadro de lista **Copia de seguridad en** .</span><span class="sxs-lookup"><span data-stu-id="2035f-161">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="2035f-162">Para eliminar un destino de copia de seguridad, selecciónelo y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="2035f-162">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="2035f-163">Para ver el contenido de un destino de copia de seguridad, selecciónelo y haga clic en **Contenido**.</span><span class="sxs-lookup"><span data-stu-id="2035f-163">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="2035f-164">Para ver o seleccionar las opciones multimedia, haga clic en **Opciones multimedia** en el panel **Seleccionar una página** .</span><span class="sxs-lookup"><span data-stu-id="2035f-164">To view or select the media options, click **Media Options** in the **Select a page** pane.</span></span>  
  
13. <span data-ttu-id="2035f-165">Seleccione una opción de **Sobrescribir medios** ; para ello, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2035f-165">Select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="2035f-166">**Hacer copia de seguridad en el conjunto de medios existente**</span><span class="sxs-lookup"><span data-stu-id="2035f-166">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="2035f-167">Para esta opción, haga clic en **Anexar al conjunto de copia de seguridad existente** o **Sobrescribir todos los conjuntos de copia de seguridad existentes**.</span><span class="sxs-lookup"><span data-stu-id="2035f-167">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span> <span data-ttu-id="2035f-168">Para obtener más información, vea [Conjuntos de medios, familias de medios y conjuntos de copias de seguridad &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2035f-168">For more information, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="2035f-169">Opcionalmente, seleccione **Comprobar nombre de conjunto de medios y fecha de expiración del conjunto de copia de seguridad** para que la operación de copia de seguridad compruebe la fecha y la hora en que expiran el conjunto de medios y el conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2035f-169">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="2035f-170">También puede escribir un nombre en el cuadro de texto **Nombre del conjunto de medios** .</span><span class="sxs-lookup"><span data-stu-id="2035f-170">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="2035f-171">Si no especifica ningún nombre, se creará un conjunto de medios con un nombre en blanco.</span><span class="sxs-lookup"><span data-stu-id="2035f-171">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="2035f-172">Si especifica un nombre para el conjunto, los medios (cinta o disco) se comprueban para ver si el nombre real coincide con el nombre especificado aquí.</span><span class="sxs-lookup"><span data-stu-id="2035f-172">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="2035f-173">Esta opción está deshabilitada si seleccionó **Dirección URL** como destino de la copia de seguridad en la página **General** .</span><span class="sxs-lookup"><span data-stu-id="2035f-173">This option is disabled if you selected **URL** as the backup destination in the **General** page.</span></span> <span data-ttu-id="2035f-174">Para obtener más información, vea [Copia de seguridad de la base de datos &#40;página Opciones multimedia&#41;](back-up-database-media-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="2035f-174">For more information, see [Back Up Database &#40;Media Options Page&#41;](back-up-database-media-options-page.md)</span></span>  
        >   
        >  <span data-ttu-id="2035f-175">Si piensa usar cifrado, no seleccione esta opción.</span><span class="sxs-lookup"><span data-stu-id="2035f-175">If you plan to use encryption, do not select this option.</span></span> <span data-ttu-id="2035f-176">Si selecciona esta opción, las opciones de cifrado de la página **Opciones de copia de seguridad** estarán deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="2035f-176">If you select this option, the encryption options in the **Backup Options** page will be disabled.</span></span> <span data-ttu-id="2035f-177">No se admite el cifrado al anexar al conjunto de copia de seguridad existente.</span><span class="sxs-lookup"><span data-stu-id="2035f-177">Encryption is not supported when appending to the existing backup set.</span></span>  
  
    -   <span data-ttu-id="2035f-178">**Hacer copia de seguridad en un nuevo conjunto de medios y borrar todos los conjuntos de copia de seguridad existentes**</span><span class="sxs-lookup"><span data-stu-id="2035f-178">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="2035f-179">Para esta opción, especifique un nombre en el cuadro de texto **Nuevo nombre del conjunto de medios** y, si lo desea, describa el conjunto de medios en el cuadro de texto **Nueva descripción del conjunto de medios** .</span><span class="sxs-lookup"><span data-stu-id="2035f-179">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="2035f-180">Esta opción está deshabilitada si seleccionó **Dirección URL** en la página **General** .</span><span class="sxs-lookup"><span data-stu-id="2035f-180">This option is disabled if you selected **URL** in the **General** page.</span></span> <span data-ttu-id="2035f-181">Estas acciones no se admiten cuando se realiza una copia de seguridad en Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="2035f-181">These actions are not supported when backing up to Azure storage.</span></span>  
  
14. <span data-ttu-id="2035f-182">En la sección **confiabilidad** , seleccione opcionalmente:</span><span class="sxs-lookup"><span data-stu-id="2035f-182">In the **Reliability** section, optionally check:</span></span>  
  
    -   <span data-ttu-id="2035f-183">**Comprobar copia de seguridad al finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2035f-183">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="2035f-184">**Realizar suma de comprobación antes de escribir en los medios**y, si lo desea, **Continuar después de un error de suma de comprobación**.</span><span class="sxs-lookup"><span data-stu-id="2035f-184">**Perform checksum before writing to media**, and, optionally, **Continue on checksum error**.</span></span> <span data-ttu-id="2035f-185">Para obtener más información sobre las sumas de comprobación, vea [Errores posibles de medios durante copia de seguridad y restauración &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2035f-185">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
15. <span data-ttu-id="2035f-186">Si va a realizar copias de seguridad en una unidad de cinta (según se haya especificado en la sección **Destino** de la página **General** ), la opción **Descargar la cinta después de realizar la copia de seguridad** está activa.</span><span class="sxs-lookup"><span data-stu-id="2035f-186">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="2035f-187">Al hacer clic en esta opción se activa la opción **Rebobinar la cinta antes de descargar** .</span><span class="sxs-lookup"><span data-stu-id="2035f-187">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2035f-188">Las opciones de la sección **Registro de transacciones** se encuentran inactivas salvo que vaya a realizar una copia de seguridad de un registro de transacciones (según se haya especificado en la sección **Tipo de copia de seguridad** de la página **General** ).</span><span class="sxs-lookup"><span data-stu-id="2035f-188">The options in the **Transaction log** section are inactive unless you are backing up a transaction log (as specified in the **Backup type** section of the **General** page).</span></span>  
  
16. <span data-ttu-id="2035f-189">Para ver o seleccionar las opciones de copia de seguridad, haga clic en **Opciones de copia de seguridad** en el panel **Seleccionar una página**.</span><span class="sxs-lookup"><span data-stu-id="2035f-189">To view or select the backup options, click **Backup Options** in the **Select a page** pane.</span></span>  
  
17. <span data-ttu-id="2035f-190">Especifique cuándo expirará el conjunto de copia de seguridad y se podrá sobrescribir sin omitir explícitamente la comprobación de los datos de expiración:</span><span class="sxs-lookup"><span data-stu-id="2035f-190">Specify when the backup set will expire and can be overwritten without explicitly skipping verification of the expiration data:</span></span>  
  
    -   <span data-ttu-id="2035f-191">Para que el conjunto de copia de seguridad expire al cabo de un número de días específico, haga clic en **Después de** (opción predeterminada) y escriba el número de días tras la creación del conjunto en que este expirará.</span><span class="sxs-lookup"><span data-stu-id="2035f-191">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="2035f-192">Este valor puede estar entre 0 y 99999 días; el valor 0 significa que el conjunto de copia de seguridad no expirará nunca.</span><span class="sxs-lookup"><span data-stu-id="2035f-192">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="2035f-193">El valor predeterminado se establece en la opción **Tiempo predeterminado de retención de medios de copia de seguridad (días)** del cuadro de diálogo **Propiedades del servidor** (página Configuración de base de datos).</span><span class="sxs-lookup"><span data-stu-id="2035f-193">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (Database Settings Page).</span></span> <span data-ttu-id="2035f-194">Para acceder a esta opción, en el Explorador de objetos, haga clic con el botón derecho en el nombre del servidor y seleccione Propiedades; después, seleccione la página **Configuración de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="2035f-194">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="2035f-195">Para que el conjunto de copia de seguridad expire en una determinada fecha, haga clic en **El**y escriba la fecha en la que expirará.</span><span class="sxs-lookup"><span data-stu-id="2035f-195">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
         <span data-ttu-id="2035f-196">Para obtener más información sobre las fechas de expiración de la copia de seguridad, vea [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2035f-196">For more information about backup expiration dates, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
18. [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="2035f-197">y las versiones posteriores admiten la [compresión de copia de seguridad](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2035f-197">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="2035f-198">De forma predeterminada, el hecho de que se comprima una copia de seguridad depende del valor de la opción de configuración del servidor **backup-compression default** .</span><span class="sxs-lookup"><span data-stu-id="2035f-198">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="2035f-199">Pero, independientemente del valor predeterminado actual de nivel de servidor, puede comprimir una copia de seguridad si activa **Comprimir copia de seguridad**e impedir la compresión si activa **No comprimir copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="2035f-199">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="2035f-200">**Para ver o cambiar el valor predeterminado actual de la compresión de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="2035f-200">**To view or change the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="2035f-201">Ver o establecer la opción de configuración del servidor de compresión de copia de seguridad predeterminada</span><span class="sxs-lookup"><span data-stu-id="2035f-201">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
19. <span data-ttu-id="2035f-202">Especifique si desea utilizar cifrado para la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2035f-202">Specify whether to use encryption for the backup.</span></span> <span data-ttu-id="2035f-203">Seleccione un algoritmo de cifrado para usar para el paso de cifrado y proporcione un certificado o clave asimétrica de una lista de los certificados existentes o de claves asimétricas.</span><span class="sxs-lookup"><span data-stu-id="2035f-203">Select an encryption algorithm to use for the encryption step, and provide a Certificate or Asymmetric key from a list of existing certificates or asymmetric keys.</span></span> <span data-ttu-id="2035f-204">El cifrado se admite en SQL Server 2014 o posterior.</span><span class="sxs-lookup"><span data-stu-id="2035f-204">Encryption is supported in SQL Server 2014 or later.</span></span> <span data-ttu-id="2035f-205">Para obtener más detalles sobre las opciones de cifrado, vea [Copia de seguridad de la base de datos &#40;página Opciones de copia de seguridad&#41;](back-up-database-backup-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="2035f-205">For more details on the Encryption options, see [Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2035f-206">Como alternativa para crear copias de seguridad de la base de datos, puede utilizar el Asistente para planes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="2035f-206">Alternatively, you can use the Maintenance Plan Wizard to create database backups.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2035f-207">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2035f-207">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-full-database-backup"></a><span data-ttu-id="2035f-208">Para crear una copia de seguridad completa de la base de datos</span><span class="sxs-lookup"><span data-stu-id="2035f-208">To create a full database backup</span></span>  
  
1.  <span data-ttu-id="2035f-209">Ejecute la instrucción BACKUP DATABASE para crear la copia de seguridad de base de datos completa, especificando:</span><span class="sxs-lookup"><span data-stu-id="2035f-209">Execute the BACKUP DATABASE statement to create the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="2035f-210">El nombre de la base de datos de la que se va a realizar una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2035f-210">The name of the database to back up.</span></span>  
  
    -   <span data-ttu-id="2035f-211">El dispositivo de copia de seguridad en el que se escribe la copia de seguridad de base de datos completa.</span><span class="sxs-lookup"><span data-stu-id="2035f-211">The backup device where the full database backup is written.</span></span>  
  
     <span data-ttu-id="2035f-212">La sintaxis básica de [!INCLUDE[tsql](../../includes/tsql-md.md)] para crear una copia de seguridad de base de datos completa es:</span><span class="sxs-lookup"><span data-stu-id="2035f-212">The basic [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax for a full database backup is:</span></span>  
  
     <span data-ttu-id="2035f-213">BACKUP DATABASE *database*</span><span class="sxs-lookup"><span data-stu-id="2035f-213">BACKUP DATABASE *database*</span></span>  
  
     <span data-ttu-id="2035f-214">TO *backup_device* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="2035f-214">TO *backup_device* [ **,**...*n* ]</span></span>  
  
     <span data-ttu-id="2035f-215">[ WITH *with_options* [ **,** ...*o* ] ] ;</span><span class="sxs-lookup"><span data-stu-id="2035f-215">[ WITH *with_options* [ **,**...*o* ] ] ;</span></span>  
  
    |<span data-ttu-id="2035f-216">Opción</span><span class="sxs-lookup"><span data-stu-id="2035f-216">Option</span></span>|<span data-ttu-id="2035f-217">Descripción</span><span class="sxs-lookup"><span data-stu-id="2035f-217">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="2035f-218">*database*</span><span class="sxs-lookup"><span data-stu-id="2035f-218">*database*</span></span>|<span data-ttu-id="2035f-219">Es la base de datos cuya copia de seguridad se desea hacer.</span><span class="sxs-lookup"><span data-stu-id="2035f-219">Is the database that is to be backed up.</span></span>|  
    |<span data-ttu-id="2035f-220">*backup_device* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="2035f-220">*backup_device* [ **,**...*n* ]</span></span>|<span data-ttu-id="2035f-221">Especifica una lista de 1 a 64 dispositivos de copia de seguridad que se pueden utilizar en la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2035f-221">Specifies a list of from 1 to 64 backup devices to use for the backup operation.</span></span> <span data-ttu-id="2035f-222">Puede especificar un dispositivo físico de copia de seguridad o puede especificar un dispositivo de copia de seguridad lógico correspondiente, si ya se definió.</span><span class="sxs-lookup"><span data-stu-id="2035f-222">You can specify a physical backup device, or you can specify a corresponding logical backup device, if already defined.</span></span> <span data-ttu-id="2035f-223">Para especificar un dispositivo de copia de seguridad físico, use la opción DISK o TAPE:</span><span class="sxs-lookup"><span data-stu-id="2035f-223">To specify a physical backup device, use the DISK or TAPE option:</span></span><br /><br /> <span data-ttu-id="2035f-224">{ DISK &#124; TAPE } **=** _physical_backup_device_name_</span><span class="sxs-lookup"><span data-stu-id="2035f-224">{ DISK &#124; TAPE } **=**_physical_backup_device_name_</span></span><br /><br /> <span data-ttu-id="2035f-225">Para obtener más información, vea [Dispositivos de copia de seguridad &#40;SQL Server&#41;](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2035f-225">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>|  
    |<span data-ttu-id="2035f-226">WITH *with_options* [ **,** ...*o* ]</span><span class="sxs-lookup"><span data-stu-id="2035f-226">WITH *with_options* [ **,**...*o* ]</span></span>|<span data-ttu-id="2035f-227">De forma opcional, puede especificar una o varias opciones, *o*.</span><span class="sxs-lookup"><span data-stu-id="2035f-227">Optionally, specifies one or more additional options, *o*.</span></span> <span data-ttu-id="2035f-228">Para obtener información sobre algunas de las opciones de WITH básicas, vea el paso 2.</span><span class="sxs-lookup"><span data-stu-id="2035f-228">For information about some of the basic with options, see step 2.</span></span>|  
  
2.  <span data-ttu-id="2035f-229">Opcionalmente, especifique una o varias opciones de WITH.</span><span class="sxs-lookup"><span data-stu-id="2035f-229">Optionally, specify one or more WITH options.</span></span> <span data-ttu-id="2035f-230">A continuación se describen algunas de las opciones de WITH básicas.</span><span class="sxs-lookup"><span data-stu-id="2035f-230">A few basic WITH options are described here.</span></span> <span data-ttu-id="2035f-231">Para obtener información sobre todas las opciones de WITH, vea [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2035f-231">For information about all the WITH options, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
    -   <span data-ttu-id="2035f-232">Opciones de WITH básicas del conjunto de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="2035f-232">Basic backup set WITH options:</span></span>  
  
         <span data-ttu-id="2035f-233">{ COMPRESSION | NO_COMPRESSION }</span><span class="sxs-lookup"><span data-stu-id="2035f-233">{ COMPRESSION | NO_COMPRESSION }</span></span>  
         <span data-ttu-id="2035f-234">En [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] y versiones posteriores únicamente, especifica si la [compresión de copia de seguridad](backup-compression-sql-server.md) se realiza en esta copia de seguridad, lo que invalida la configuración predeterminada del servidor.</span><span class="sxs-lookup"><span data-stu-id="2035f-234">In [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] and later only, specifies whether [backup compression](backup-compression-sql-server.md) is performed on this backup, overriding the server-level default.</span></span>  
  
         <span data-ttu-id="2035f-235">ENCRYPTION (ALGORITHM, SERVER CERTIFICATE |ASYMMETRIC KEY)</span><span class="sxs-lookup"><span data-stu-id="2035f-235">ENCRYPTION (ALGORITHM,  SERVER CERTIFICATE |ASYMMETRIC KEY)</span></span>  
         <span data-ttu-id="2035f-236">En SQL Server 2014 o versiones posteriores únicamente, especifica el algoritmo de cifrado que se va a utilizar y el certificado o la clave asimétrica que se va a usar para proteger el cifrado.</span><span class="sxs-lookup"><span data-stu-id="2035f-236">In SQL Server 2014 or later only, specify the encryption algorithm to use, and the Certificate or Asymmetric key to use to secure the encryption.</span></span>  
  
         <span data-ttu-id="2035f-237">Descripción **=** { **' *`text`* '**  |  **@** _text_variable_ }</span><span class="sxs-lookup"><span data-stu-id="2035f-237">DESCRIPTION **=** { **'*`text`*'** | **@**_text_variable_ }</span></span>  
         <span data-ttu-id="2035f-238">Especifica el texto sin formato que describe el conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2035f-238">Specifies the free-form text that describes the backup set.</span></span> <span data-ttu-id="2035f-239">La cadena puede tener un máximo de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="2035f-239">The string can have a maximum of 255 characters.</span></span>  
  
         <span data-ttu-id="2035f-240">Nombre **=** { *backup_set_name*  |  **@** _backup_set_name_var_ }</span><span class="sxs-lookup"><span data-stu-id="2035f-240">NAME **=** { *backup_set_name* | **@**_backup_set_name_var_ }</span></span>  
         <span data-ttu-id="2035f-241">Especifica el nombre del conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2035f-241">Specifies the name of the backup set.</span></span> <span data-ttu-id="2035f-242">Los nombres pueden tener un máximo de 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="2035f-242">Names can have a maximum of 128 characters.</span></span> <span data-ttu-id="2035f-243">Si no se especifica NAME, está en blanco.</span><span class="sxs-lookup"><span data-stu-id="2035f-243">If NAME is not specified, it is blank.</span></span>  
  
    -   <span data-ttu-id="2035f-244">Opciones de WITH básicas del conjunto de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="2035f-244">Basic backup set WITH options:</span></span>  
  
         <span data-ttu-id="2035f-245">De forma predeterminada, BACKUP DATABASE anexa la copia de seguridad a un conjunto de medios existente, conservando los conjuntos de copia de seguridad existentes.</span><span class="sxs-lookup"><span data-stu-id="2035f-245">By default, BACKUP appends the backup to an existing media set, preserving existing backup sets.</span></span> <span data-ttu-id="2035f-246">Para especificar esto explícitamente, utilice la opción NOINIT.</span><span class="sxs-lookup"><span data-stu-id="2035f-246">To explicitly specify this, use the NOINIT option.</span></span> <span data-ttu-id="2035f-247">Para obtener información sobre la anexión a conjuntos de copia de seguridad existentes, vea [Conjuntos de medios, familias de medios y conjuntos de copias de seguridad &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2035f-247">For information about appending to existing backup sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
         <span data-ttu-id="2035f-248">Opcionalmente, para dar formato a los medios de copia de seguridad, utilice la opción FORMAT:</span><span class="sxs-lookup"><span data-stu-id="2035f-248">Alternatively, to format the backup media, use the FORMAT option:</span></span>  
  
         <span data-ttu-id="2035f-249">Format [ **,** MEDIANAME **=** { *media_name*  |  **@** _media_name_variable_ }] [ **,** MEDIADESCRIPTION **=** { *Text*  |  **@** _text_variable_ }]</span><span class="sxs-lookup"><span data-stu-id="2035f-249">FORMAT [ **,** MEDIANAME**=** { *media_name* | **@**_media_name_variable_ } ] [ **,** MEDIADESCRIPTION **=** { *text* | **@**_text_variable_ } ]</span></span>  
         <span data-ttu-id="2035f-250">Utilice la cláusula FORMAT cuando emplee los medios por primera vez o cuando desee sobrescribir todos los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="2035f-250">Use the FORMAT clause when you are using media for the first time or you want to overwrite all existing data.</span></span> <span data-ttu-id="2035f-251">De manera opcional, puede asignar a los nuevos medios un nombre y una descripción.</span><span class="sxs-lookup"><span data-stu-id="2035f-251">Optionally, assign the new media a media name and description.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="2035f-252">Tenga mucho cuidado cuando utilice la cláusula FORMAT de la instrucción BACKUP, ya que destruye cualquier copia de seguridad existente en el medio de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2035f-252">Use extreme caution when you are using the FORMAT clause of the BACKUP statement because this destroys any backups that were previously stored on the backup media.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="2035f-253">Ejemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2035f-253">Examples (Transact-SQL)</span></span>  
  
#### <a name="a-backing-up-to-a-disk-device"></a><span data-ttu-id="2035f-254">A.</span><span class="sxs-lookup"><span data-stu-id="2035f-254">A.</span></span> <span data-ttu-id="2035f-255">Realizar la copia de seguridad en un dispositivo de disco</span><span class="sxs-lookup"><span data-stu-id="2035f-255">Backing up to a disk device</span></span>  
 <span data-ttu-id="2035f-256">En el ejemplo siguiente se realiza una copia de seguridad completa de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] en el disco y se usa `FORMAT` para crear un conjunto de medios nuevo.</span><span class="sxs-lookup"><span data-stu-id="2035f-256">The following example backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to disk, by using `FORMAT` to create a new media set.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
   WITH FORMAT,  
      MEDIANAME = 'Z_SQLServerBackups',  
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
#### <a name="b-backing-up-to-a-tape-device"></a><span data-ttu-id="2035f-257">B.</span><span class="sxs-lookup"><span data-stu-id="2035f-257">B.</span></span> <span data-ttu-id="2035f-258">Realizar la copia de seguridad en un dispositivo de cinta</span><span class="sxs-lookup"><span data-stu-id="2035f-258">Backing up to a tape device</span></span>  
 <span data-ttu-id="2035f-259">En este ejemplo se realiza una copia de seguridad en cinta de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]completa y se anexa a las copias de seguridad anteriores.</span><span class="sxs-lookup"><span data-stu-id="2035f-259">The following example backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]database to tape, appending the backup to the previous backups.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
   TO TAPE = '\\.\Tape0'  
   WITH NOINIT,  
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
#### <a name="c-backing-up-to-a-logical-tape-device"></a><span data-ttu-id="2035f-260">C.</span><span class="sxs-lookup"><span data-stu-id="2035f-260">C.</span></span> <span data-ttu-id="2035f-261">Realizar la copia de seguridad en un dispositivo de cinta lógico</span><span class="sxs-lookup"><span data-stu-id="2035f-261">Backing up to a logical tape device</span></span>  
 <span data-ttu-id="2035f-262">En este ejemplo, se crea un dispositivo de copia de seguridad lógico para una unidad de cinta.</span><span class="sxs-lookup"><span data-stu-id="2035f-262">The following example creates a logical backup device for a tape drive.</span></span> <span data-ttu-id="2035f-263">A continuación, se realiza una copia de seguridad completa de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] en dicho dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2035f-263">The example then backs up the complete [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to that device.</span></span>  
  
```sql  
-- Create a logical backup device,   
-- AdventureWorks2012_Bak_Tape, for tape device \\.\tape0.  
USE master;  
GO  
EXEC sp_addumpdevice 'tape', 'AdventureWorks2012_Bak_Tape', '\\.\tape0'; USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
   TO AdventureWorks2012_Bak_Tape  
   WITH FORMAT,  
      MEDIANAME = 'AdventureWorks2012_Bak_Tape',  
      MEDIADESCRIPTION = '\\.\tape0',   
      NAME = 'Full Backup of AdventureWorks2012';  
GO  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="2035f-264">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="2035f-264">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="2035f-265">Utilice el cmdlet `Backup-SqlDatabase`.</span><span class="sxs-lookup"><span data-stu-id="2035f-265">Use the `Backup-SqlDatabase` cmdlet.</span></span> <span data-ttu-id="2035f-266">Para indicar explícitamente que se trata de una copia de seguridad completa de la base de datos, especifique el parámetro **-BackupAction** con su valor predeterminado, `Database` .</span><span class="sxs-lookup"><span data-stu-id="2035f-266">To explicitly indicate that this is a full database backup, specify the **-BackupAction**  parameter with its default value, `Database`.</span></span> <span data-ttu-id="2035f-267">Este parámetro es opcional para las copias de seguridad de base de datos completas.</span><span class="sxs-lookup"><span data-stu-id="2035f-267">This parameter is optional for full database backups.</span></span>  
  
     <span data-ttu-id="2035f-268">En el ejemplo siguiente se crea una copia de seguridad completa de la base de datos `MyDB` en la ubicación de copia de seguridad predeterminada de la instancia de servidor `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="2035f-268">The following example creates a full database backup of the `MyDB` database to the default backup location of the server instance `Computer\Instance`.</span></span> <span data-ttu-id="2035f-269">Opcionalmente, en este ejemplo se especifica `-BackupAction Database`.</span><span class="sxs-lookup"><span data-stu-id="2035f-269">Optionally, this example specifies `-BackupAction Database`.</span></span>  
  
    ```powershell
    Backup-SqlDatabase -ServerInstance Computer\Instance -Database MyDB -BackupAction Database  
    ```  
  
 <span data-ttu-id="2035f-270">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2035f-270">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="2035f-271">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="2035f-271">SQL Server PowerShell Provider</span></span>](../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2035f-272">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="2035f-272">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2035f-273">Realizar una copia de seguridad de una base de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2035f-273">Back Up a Database (SQL Server)</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="2035f-274">Crear una copia de seguridad diferencial de una base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2035f-274">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="2035f-275">Restaurar una copia de seguridad de base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2035f-275">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="2035f-276">Restaurar una copia de seguridad de base de datos en el modelo de recuperación simple &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2035f-276">Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md)  
  
-   [<span data-ttu-id="2035f-277">Restaurar una base de datos según el punto de error en el modelo de recuperación completa &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2035f-277">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="2035f-278">Restaurar una base de datos a una nueva ubicación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2035f-278">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="2035f-279">Usar el Asistente para planes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="2035f-279">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="2035f-280">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2035f-280">See Also</span></span>  
 <span data-ttu-id="2035f-281">[Información general de copia de seguridad &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2035f-281">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="2035f-282">[Copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2035f-282">[Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="2035f-283">[Conjuntos de medios, familias de medios y conjuntos de copias de seguridad &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2035f-283">[Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span></span>  
 <span data-ttu-id="2035f-284">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2035f-284">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="2035f-285">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2035f-285">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="2035f-286">[Copia de seguridad de base de datos &#40;página General&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="2035f-286">[Back Up Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="2035f-287">[Copia de seguridad de la base de datos &#40;página Opciones de copia de seguridad&#41;](back-up-database-backup-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="2035f-287">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) </span></span>  
 <span data-ttu-id="2035f-288">[Copias de seguridad diferenciales &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2035f-288">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="2035f-289">Copias de seguridad completas de bases de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2035f-289">Full Database Backups &#40;SQL Server&#41;</span></span>](full-database-backups-sql-server.md)  
