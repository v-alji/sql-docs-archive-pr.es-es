---
title: Preparar una base de datos reflejada para la creación de reflejo (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], preparing for mirroring
- logins [SQL Server], database mirroring
- mirror database [SQL Server]
ms.assetid: 8676f9d8-c451-419b-b934-786997d46c2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf46b4f6fd8e7af55e1930ef6063c4754673fa79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746510"
---
# <a name="prepare-a-mirror-database-for-mirroring-sql-server"></a><span data-ttu-id="b23b8-102">Preparar una base de datos reflejada para la creación de reflejo (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b23b8-102">Prepare a Mirror Database for Mirroring (SQL Server)</span></span>
  <span data-ttu-id="b23b8-103">Para poder empezar una sesión de creación de reflejo de la base de datos, el propietario de la base de datos o el administrador del sistema debe asegurarse de que la base de datos reflejada se ha creado y está preparada para la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="b23b8-103">Before a database mirroring session can start, the database owner or system administrator must make sure that the mirror database has been created and is ready for mirroring.</span></span> <span data-ttu-id="b23b8-104">La creación de una base de datos reflejada requiere como mínimo que se haga una copia de seguridad completa de la base de datos principal y la subsiguiente copia de seguridad de registros, y que ambas se restauren en la instancia del servidor reflejado mediante WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="b23b8-104">Creating a new mirror database minimally requires taking a full backup of the principal database and a subsequent log backup and restoring them both onto the mirror server instance, using WITH NORECOVERY.</span></span>  
  
 <span data-ttu-id="b23b8-105">En este tema se describe cómo preparar una base de datos reflejada en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b23b8-105">This topic describes how to prepare a mirror database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b23b8-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="b23b8-106">Before You Begin</span></span>  
  
###  <a name="requirements"></a><a name="Requirements"></a> <span data-ttu-id="b23b8-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b23b8-107">Requirements</span></span>  
  
-   <span data-ttu-id="b23b8-108">Las instancias de servidor principal y reflejado deben ejecutarse en la misma versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b23b8-108">The principal and mirror server instances must be running on the same version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b23b8-109">Aunque es posible que el servidor reflejado tenga una versión posterior de SQL Server, esta configuración solo se recomienda durante un proceso de actualización planeado cuidadosamente.</span><span class="sxs-lookup"><span data-stu-id="b23b8-109">While it is possible for the mirror server to have a higher version of SQL Server, this configuration is only recommended during a carefully planned upgrade process.</span></span> <span data-ttu-id="b23b8-110">En tal configuración, se corre el riesgo de una conmutación por error automática, en la que el movimiento de datos se suspende automáticamente debido a que los datos no pueden pasarse a una versión inferior de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b23b8-110">In such a configuration, you run the risk of an automatic failover, in which data movement is automatically suspended because data cannot move to a lower version of SQL Server.</span></span> <span data-ttu-id="b23b8-111">Para más información, consulte [Minimize Downtime for Mirrored Databases When Upgrading Server Instances](upgrading-mirrored-instances.md).</span><span class="sxs-lookup"><span data-stu-id="b23b8-111">For more information, see [Minimize Downtime for Mirrored Databases When Upgrading Server Instances](upgrading-mirrored-instances.md).</span></span>  
  
-   <span data-ttu-id="b23b8-112">Las instancias de servidor principal y reflejado deben ejecutarse en la misma edición de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b23b8-112">The principal and mirror server instances must be running on the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b23b8-113">Para más información sobre la compatibilidad con la creación de reflejo de la base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], vea [Características compatibles con las ediciones de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="b23b8-113">For information about support for database mirroring in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="b23b8-114">La base de datos debe usar el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="b23b8-114">The database must use the full recovery model.</span></span>  
  
     <span data-ttu-id="b23b8-115">Para obtener más información, vea [Ver o cambiar el modelo de recuperación de una base de datos &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md) o [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) y [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b23b8-115">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md) or [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) and [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
-   <span data-ttu-id="b23b8-116">La base de datos reflejada debe tener el mismo nombre que la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="b23b8-116">The name of the mirror database must be the same as the name of the principal database.</span></span>  
  
-   <span data-ttu-id="b23b8-117">Para que la creación de reflejo funcione, la base de datos reflejada debe permanecer en estado RESTORING.</span><span class="sxs-lookup"><span data-stu-id="b23b8-117">The mirror database must be in the RESTORING state for mirroring to work.</span></span> <span data-ttu-id="b23b8-118">Al preparar una base de datos reflejada, debe usar RESTORE WITH NORECOVERY para cada operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="b23b8-118">When preparing a mirror database, you must use RESTORE WITH NORECOVERY for every restore operation.</span></span> <span data-ttu-id="b23b8-119">Como mínimo, necesitará restaurar (WITH NORECOVERY) una copia de seguridad completa de la base de datos principal, seguida de todas las copias de seguridad de registros subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="b23b8-119">Minimally, you will need to restore WITH NORECOVERY a full backup of the principal database, followed by all subsequent log backups.</span></span>  
  
-   <span data-ttu-id="b23b8-120">El sistema donde piensa crear la base de datos reflejada debe poseer una unidad de disco con espacio suficiente para alojar la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="b23b8-120">The system where you plan to create the mirror database must possesses a disk drive with sufficient space to hold the mirror database.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b23b8-121">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="b23b8-121">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b23b8-122">No puede reflejar las bases de datos del sistema **master**, **msdb**, **temp**o **model** .</span><span class="sxs-lookup"><span data-stu-id="b23b8-122">You cannot mirror the **master**, **msdb**, **temp**, or **model** system databases.</span></span>  
  
-   <span data-ttu-id="b23b8-123">No se puede reflejar una base de datos que pertenece a un [grupos de disponibilidad AlwaysOn (SQL Server)](../availability-groups/windows/always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b23b8-123">You cannot mirror a database that belongs to an [AlwaysOn Availability Groups (SQL Server)](../availability-groups/windows/always-on-availability-groups-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b23b8-124">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="b23b8-124">Recommendations</span></span>  
  
-   <span data-ttu-id="b23b8-125">Use una copia de seguridad completa muy reciente o una copia de seguridad diferencial reciente de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="b23b8-125">Use a very recent full database backup or a recent differential database backup of the principal database.</span></span>  
  
-   <span data-ttu-id="b23b8-126">Si se programa un trabajo de copia de seguridad de registros para que se ejecute muy a menudo en la base de datos principal, puede que sea necesario deshabilitar el trabajo de copia de seguridad hasta que se haya iniciado la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="b23b8-126">If a log backup job is scheduled to run very frequently on the principal database, you might have to disable the backup job until mirroring has started.</span></span>  
  
-   <span data-ttu-id="b23b8-127">Si es posible, la ruta de acceso (incluida la letra de unidad) de la base de datos reflejada debería ser idéntica a la de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="b23b8-127">If possible, the path (including the drive letter) of the mirror database should be identical to the path of the principal database.</span></span>  
  
     <span data-ttu-id="b23b8-128">Si las rutas de acceso de archivo deben ser diferentes (por ejemplo, si la base de datos principal se encuentra en la unidad 'F:' pero el sistema reflejado no tiene unidad F:), se debe incluir la opción MOVE en RESTORE STATEMENT.</span><span class="sxs-lookup"><span data-stu-id="b23b8-128">If the file paths must differ, for example, if the principal database is on drive 'F:' but the mirror system lacks an F: drive, you must include the MOVE option in the RESTORE STATEMENT.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b23b8-129">Para poder agregar un archivo durante una sesión de creación de reflejo sin influir en la sesión, la ruta de acceso del archivo debe existir en ambos servidores.</span><span class="sxs-lookup"><span data-stu-id="b23b8-129">Adding a file during a mirroring session without impacting the session requires that the path of the file exists on both servers.</span></span> <span data-ttu-id="b23b8-130">Por consiguiente, si mueve los archivos de base de datos al crear la base de datos reflejada, se podría producir un error en una operación posterior para agregar un archivo en la base de datos reflejada y provocar la suspensión de la creación del reflejo.</span><span class="sxs-lookup"><span data-stu-id="b23b8-130">Therefore, if you move the database files when creating the mirror database, a later add-file operation might fail on the mirror database and cause mirroring to be suspended.</span></span> <span data-ttu-id="b23b8-131">Para obtener información sobre cómo actuar si una operación de creación de archivo no ha podido realizarse, vea [Solucionar problemas de configuración de creación de reflejo de la base de datos &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b23b8-131">For information about dealing with a failed create-file operation, see [Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md).</span></span>  
  
-   <span data-ttu-id="b23b8-132">Si la base de datos principal tiene algunos catálogos de texto completo, se recomienda ver [Creación de reflejo de la base de datos y catálogos de texto completo &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b23b8-132">If the principal database has any full-text catalogs, we recommend that you see [Database Mirroring and Full-Text Catalogs &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md).</span></span>  
  
-   <span data-ttu-id="b23b8-133">Para una base de datos de producción, realice siempre la copia de seguridad en un dispositivo diferente.</span><span class="sxs-lookup"><span data-stu-id="b23b8-133">For a production database, always back up to a separate device.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b23b8-134">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b23b8-134">Security</span></span>  
 <span data-ttu-id="b23b8-135">TRUSTWORTHY se establece en OFF cuando se hace una copia de seguridad de base de datos.</span><span class="sxs-lookup"><span data-stu-id="b23b8-135">TRUSTWORTHY is set to OFF when a database is backed up.</span></span> <span data-ttu-id="b23b8-136">Por lo tanto, TRUSTWORTHY está siempre en OFF en una nueva base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="b23b8-136">Therefore, TRUSTWORTHY is always OFF on a new mirror database.</span></span> <span data-ttu-id="b23b8-137">Si es preciso que la base de datos sea de confianza después de una conmutación por error, son necesarios pasos de configuración adicionales.</span><span class="sxs-lookup"><span data-stu-id="b23b8-137">If the database needs to be trustworthy after a failover, additional setup steps are necessary.</span></span> <span data-ttu-id="b23b8-138">Para más información, consulte [Configurar una base de datos reflejada para usar la propiedad Trustworthy &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b23b8-138">For more information, see [Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span></span>  
  
 <span data-ttu-id="b23b8-139">Para obtener más información sobre cómo habilitar el descifrado automático de la clave maestra de la base de datos de una base de datos reflejada, vea [Establecer una base de datos reflejada cifrada](set-up-an-encrypted-mirror-database.md).</span><span class="sxs-lookup"><span data-stu-id="b23b8-139">For information about enabling automatic decryption of the database master key of a mirror database, see [Set Up an Encrypted Mirror Database](set-up-an-encrypted-mirror-database.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b23b8-140">Permisos</span><span class="sxs-lookup"><span data-stu-id="b23b8-140">Permissions</span></span>  
 <span data-ttu-id="b23b8-141">Propietario de la base de datos o administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="b23b8-141">Database owner or system administrator.</span></span>  
  
##  <a name="to-prepare-an-existing-mirror-database-to-restart-mirroring"></a><a name="PrepareToRestartMirroring"></a> <span data-ttu-id="b23b8-142">Para preparar una base de datos reflejada existente para reiniciar la creación de reflejo</span><span class="sxs-lookup"><span data-stu-id="b23b8-142">To Prepare an Existing Mirror Database to Restart Mirroring</span></span>  
 <span data-ttu-id="b23b8-143">Si la creación de reflejo se ha eliminado y la base de datos reflejada sigue en el estado de recuperación (RECOVERING), se puede reiniciar la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="b23b8-143">If mirroring has been removed and the mirror database is still in the RECOVERING state, you can restart mirroring.</span></span>  
  
1.  <span data-ttu-id="b23b8-144">Realice al menos una copia de seguridad de registros de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="b23b8-144">Take at least one log backup on the principal database.</span></span> <span data-ttu-id="b23b8-145">Para obtener más información, vea [Realizar copia de seguridad de un registro de transacciones &#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="b23b8-145">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="b23b8-146">En la base de datos reflejada, use RESTORE WITH NORECOVERY para restaurar todas las copias de seguridad de registros que se realizaron en la base de datos principal desde que se quitó la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="b23b8-146">On the mirror database, use RESTORE WITH NORECOVERY to restore all log backups taken on the principal database since mirroring was removed.</span></span> <span data-ttu-id="b23b8-147">Para más información, consulte [Restaurar una copia de seguridad del registro de transacciones &#40;SQL Server&#41;](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b23b8-147">For more information, see [Restore a Transaction Log Backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md).</span></span>  
  
##  <a name="to-prepare-a-new-mirror-database"></a><a name="CombinedProcedure"></a> <span data-ttu-id="b23b8-148">Para preparar una nueva base de datos reflejada</span><span class="sxs-lookup"><span data-stu-id="b23b8-148">To Prepare a New Mirror Database</span></span>  
 <span data-ttu-id="b23b8-149">**Para preparar una base de datos reflejada**</span><span class="sxs-lookup"><span data-stu-id="b23b8-149">**To prepare a mirror database**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b23b8-150">Para obtener un ejemplo de [!INCLUDE[tsql](../../includes/tsql-md.md)] de este procedimiento, vea [Ejemplo (Transact-SQL)](#TsqlExample)más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="b23b8-150">For a [!INCLUDE[tsql](../../includes/tsql-md.md)] example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="b23b8-151">Conéctese a la instancia del servidor principal.</span><span class="sxs-lookup"><span data-stu-id="b23b8-151">Connect to principal server instance.</span></span>  
  
2.  <span data-ttu-id="b23b8-152">Cree una copia de seguridad completa o una copia de seguridad diferencial de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="b23b8-152">Create either a full database backup or a differential database backup of the principal database.</span></span>  
  
    -   [<span data-ttu-id="b23b8-153">Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b23b8-153">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
    -   <span data-ttu-id="b23b8-154">[Crear una copia de seguridad diferencial de una base de datos &#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b23b8-154">[Create a Differential Database Backup &#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-differential-database-backup-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="b23b8-155">Normalmente, necesita realizar al menos una copia de seguridad de registros de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="b23b8-155">Typically, you need to take at least one log backup on the principal database.</span></span> <span data-ttu-id="b23b8-156">Sin embargo, puede que no se necesite una copia de seguridad de registros si la base de datos se ha creado recientemente y no se ha hecho todavía ninguna copia de seguridad de registros o si el modelo de recuperación ha cambiado recientemente de SIMPLE a FULL.</span><span class="sxs-lookup"><span data-stu-id="b23b8-156">However, a log backup might be unnecessary, if the database has just been created and no log backup has been taken yet, or if the recovery model has just been changed from SIMPLE to FULL.</span></span>  
  
    -   [<span data-ttu-id="b23b8-157">Realizar una copia de seguridad de un registro de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b23b8-157">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md)  
  
4.  <span data-ttu-id="b23b8-158">A menos que las copias de seguridad estén en una unidad de red que sea accesible desde ambos sistemas, copie las copias de seguridad de la base de datos y de registros al sistema que hospedará la instancia de servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="b23b8-158">Unless the backups are on a network drive that is accessible from both systems, copy the database and log backups to the system that will host the mirror server instance.</span></span>  
  
5.  <span data-ttu-id="b23b8-159">Conéctese a la instancia del servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="b23b8-159">Connect to mirror server instance.</span></span>  
  
6.  <span data-ttu-id="b23b8-160">Con RESTORE WITH NORECOVERY, cree la base de datos reflejada restaurando la copia de seguridad completa y, opcionalmente, la copia de seguridad diferencial más reciente, en la instancia de servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="b23b8-160">Using RESTORE WITH NORECOVERY, create the mirror database by restoring the full database backup and, optionally, the most recent differential database backup, onto the mirror server instance.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b23b8-161">Si restaura la base de datos grupo de archivos por grupo de archivos, asegúrese de restaurar la base de datos completa.</span><span class="sxs-lookup"><span data-stu-id="b23b8-161">If you restore the database filegroup by filegroup, be sure to restore the whole database.</span></span>  
  
    -   [<span data-ttu-id="b23b8-162">Restaurar una copia de seguridad de base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b23b8-162">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](../../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md)  
  
    -   <span data-ttu-id="b23b8-163">[RESTORE &amp;#40;Transact-SQL&amp;#41;](/sql/t-sql/statements/restore-statements-transact-sql) y [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b23b8-163">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) and [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span></span>  
  
7.  <span data-ttu-id="b23b8-164">Con RESTORE WITH NORECOVERY, aplique la copia de seguridad o las copias de seguridad de registros pendientes en la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="b23b8-164">Using RESTORE WITH NORECOVERY, apply any outstanding log backup or backups to the mirror database.</span></span>  
  
    -   [<span data-ttu-id="b23b8-165">Restaurar una copia de seguridad de registros de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b23b8-165">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="b23b8-166">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b23b8-166">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="b23b8-167">Para poder iniciar una sesión de creación de reflejo de la base de datos, debe crear la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="b23b8-167">Before you can start a database mirroring session, you must create the mirror database.</span></span> <span data-ttu-id="b23b8-168">Debe hacerlo inmediatamente antes de iniciar la sesión de creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="b23b8-168">You should do this just before starting the mirroring session.</span></span>  
  
 <span data-ttu-id="b23b8-169">En este ejemplo se utiliza la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , que usa de forma predeterminada un modelo de recuperación simple.</span><span class="sxs-lookup"><span data-stu-id="b23b8-169">This example uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database, which uses the simple recovery model by default.</span></span>  
  
1.  <span data-ttu-id="b23b8-170">Para utilizar la creación de reflejo de la base de datos con la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , modifíquela para que utilice el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="b23b8-170">To use database mirroring with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, modify it to use the full recovery model:</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
    SET RECOVERY FULL;  
    GO  
    ```  
  
2.  <span data-ttu-id="b23b8-171">Después de modificar el modelo de recuperación de la base de datos de SIMPLE a FULL, cree una copia de seguridad completa, que puede usarse para crear la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="b23b8-171">After modifying the recovery model of the database from SIMPLE to FULL, create a full backup, which can be used to create the mirror database.</span></span> <span data-ttu-id="b23b8-172">Puesto que se ha cambiado recientemente el modelo de recuperación, se especifica la opción WITH FORMAT para crear un conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="b23b8-172">Because the recovery model has just been changed, the WITH FORMAT option is specified to create a new media set.</span></span> <span data-ttu-id="b23b8-173">Esto es útil para separar las copias de seguridad con el modelo de recuperación completa a partir de cualquier copia de seguridad anterior realizada con el modelo de recuperación simple.</span><span class="sxs-lookup"><span data-stu-id="b23b8-173">This is useful to separate the backups under the full recovery model from any previous backups made under the simple recovery model.</span></span> <span data-ttu-id="b23b8-174">Para este ejemplo, el archivo de copia de seguridad (`C:\AdventureWorks.bak`) se crea en la misma unidad que la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b23b8-174">For the purpose of this example, the backup file (`C:\AdventureWorks.bak`) is created on the same drive as the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b23b8-175">Para una base de datos de producción, siempre se debe realizar la copia de seguridad en un dispositivo independiente.</span><span class="sxs-lookup"><span data-stu-id="b23b8-175">For a production database, you should always back up to a separate device.</span></span>  
  
     <span data-ttu-id="b23b8-176">En la instancia de servidor principal (en `PARTNERHOST1`), cree una copia de seguridad completa de la base de datos principal, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="b23b8-176">On the principal server instance (on `PARTNERHOST1`), create a full backup of the principal database as follows:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
        WITH FORMAT  
    GO  
    ```  
  
3.  <span data-ttu-id="b23b8-177">Copie la copia de seguridad completa en el servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="b23b8-177">Copy the full backup to the mirror server.</span></span>  
  
4.  <span data-ttu-id="b23b8-178">Con RESTORE WITH NORECOVERY, restaure la copia de seguridad completa en la instancia de servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="b23b8-178">Using RESTORE WITH NORECOVERY, restore the full backup onto the mirror server instance.</span></span> <span data-ttu-id="b23b8-179">El comando de restauración depende de si las rutas de acceso de las bases de datos principal y reflejada son idénticas.</span><span class="sxs-lookup"><span data-stu-id="b23b8-179">The restore command depends on whether the paths of principal and mirror databases are identical.</span></span>  
  
    -   <span data-ttu-id="b23b8-180">**Si las rutas de acceso son idénticas:**</span><span class="sxs-lookup"><span data-stu-id="b23b8-180">**If the paths are identical:**</span></span>  
  
         <span data-ttu-id="b23b8-181">En la instancia del servidor reflejado (en `PARTNERHOST5`), restaure la copia de seguridad completa como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="b23b8-181">On the mirror server instance (on `PARTNERHOST5`), restore the full backup as follows:</span></span>  
  
        ```  
        RESTORE DATABASE AdventureWorks   
            FROM DISK = 'C:\AdventureWorks.bak'   
            WITH NORECOVERY  
        GO  
        ```  
  
    -   <span data-ttu-id="b23b8-182">**Si las rutas de acceso son distintas:**</span><span class="sxs-lookup"><span data-stu-id="b23b8-182">**If the paths differ:**</span></span>  
  
         <span data-ttu-id="b23b8-183">Si la ruta de acceso de la base de datos reflejada difiere de la de la base de datos principal (por ejemplo, letras de unidad diferentes), la creación de la base de datos reflejada requiere que la operación de restauración incluya una cláusula MOVE.</span><span class="sxs-lookup"><span data-stu-id="b23b8-183">If the path of the mirror database differs from the path of the principal database (for instance, their drive letters differ), creating the mirror database requires that the restore operation include a MOVE clause.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="b23b8-184">Si los nombres de las rutas de acceso de las bases de datos principal y reflejada son distintos, no se puede agregar ningún archivo.</span><span class="sxs-lookup"><span data-stu-id="b23b8-184">If the path names of the principal and mirror databases differ, you cannot add a file.</span></span> <span data-ttu-id="b23b8-185">Esto es debido a que al recibir el registro para la operación de agregar un archivo, la instancia del servidor reflejado intenta colocar el nuevo archivo en la ubicación utilizada por la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="b23b8-185">This is because on receiving the log for the add file operation, the mirror server instance attempts to place the new file in the location used by the principal database.</span></span>  
  
         <span data-ttu-id="b23b8-186">Por ejemplo, el siguiente comando restaura una copia de seguridad de una base de datos principal que reside en C:\Archivos de programa\Microsoft SQL Server\MSSQL.*n*\MSSQL\Data\ en una ubicación distinta, D:\Archivos de programa\Microsoft SQL Server\MSSQL.*n*\MSSQL\Dat`a\`, donde va a residir la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="b23b8-186">For example, the following command restores a backup of a principal database residing in C:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Data\ to a different location, D:\Program Files\Microsoft SQL Server\MSSQL.*n*\MSSQL\Dat`a\`, where the mirror database is to reside.</span></span>  
  
        ```  
        RESTORE DATABASE AdventureWorks  
           FROM DISK='C:\AdventureWorks.bak'  
           WITH NORECOVERY,   
              MOVE 'AdventureWorks_Data' TO   
                 'D:\Program Files\Microsoft SQL Server\MSSQL.n\MSSQL\Data\AdventureWorks_Data.mdf',   
              MOVE 'AdventureWorks_Log' TO  
                 'D:\Program Files\Microsoft SQL Server\MSSQL.n\MSSQL\Data\AdventureWorks_Log.ldf';  
        GO  
        ```  
  
5.  <span data-ttu-id="b23b8-187">Una vez creada la copia de seguridad completa, debe crearse una copia de seguridad de registros en la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="b23b8-187">After you create the full backup, you must create a log backup on the principal database.</span></span> <span data-ttu-id="b23b8-188">Por ejemplo, la siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] realiza una copia de seguridad del registro en el mismo archivo que se utilizó en la anterior copia de seguridad completa:</span><span class="sxs-lookup"><span data-stu-id="b23b8-188">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement backs up the log to the same file used by the preceding full backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="b23b8-189">Para poder iniciar la creación de reflejo, se debe aplicar la copia de seguridad de registros obligatoria (y las copias de seguridad de registros subsiguientes).</span><span class="sxs-lookup"><span data-stu-id="b23b8-189">Before you can start mirroring, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="b23b8-190">Por ejemplo, la siguiente instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] restaura el primer registro de `C:\AdventureWorks.bak`:</span><span class="sxs-lookup"><span data-stu-id="b23b8-190">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores the first log from `C:\AdventureWorks.bak`:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="b23b8-191">Si se realizan copias de seguridad de registros adicionales antes de iniciar la creación de reflejo, se deben restaurar todas las copias de seguridad de registros, por orden, en el servidor reflejado mediante WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="b23b8-191">If any additional log backups occur before you start mirroring, you must also restore all of those log backups, in sequence, to the mirror server using WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="b23b8-192">Por ejemplo, la siguiente instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] restaura dos registros adicionales de `C:\AdventureWorks.bak`:</span><span class="sxs-lookup"><span data-stu-id="b23b8-192">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores two additional logs from `C:\AdventureWorks.bak`:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=2, NORECOVERY  
    GO  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\AdventureWorks.bak'   
        WITH FILE=3, NORECOVERY  
    GO  
    ```  
  
 <span data-ttu-id="b23b8-193">Para ver un ejemplo completo de la configuración de la creación de reflejo de la base de datos, en el que se muestra la configuración de seguridad, se prepara la base de datos reflejada, se configuran los asociados y se agrega un testigo, vea [Configurar la creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b23b8-193">For a complete example of setting up database mirroring, showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-preparing-a-mirror-database"></a><a name="FollowUp"></a> <span data-ttu-id="b23b8-194">Seguimiento: Después de preparar una base de datos reflejada</span><span class="sxs-lookup"><span data-stu-id="b23b8-194">Follow Up: After Preparing a Mirror Database</span></span>  
  
1.  <span data-ttu-id="b23b8-195">Si se han realizado copias de seguridad de registros adicionales desde la operación RESTORE LOG más reciente, se debe aplicar manualmente cada copia de seguridad de registros adicional, utilizando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="b23b8-195">If any additional log backups have been taken since your most recent RESTORE LOG operation, you must manually apply every additional log backup, using RESTORE WITH NORECOVERY.</span></span>  
  
2.  <span data-ttu-id="b23b8-196">Inicie la sesión de creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="b23b8-196">Start the mirroring session.</span></span> <span data-ttu-id="b23b8-197">Para más información, consulte [Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) o [Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="b23b8-197">For more information, see [Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) or [Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md).</span></span>  
  
3.  <span data-ttu-id="b23b8-198">Si ha deshabilitado el trabajo de copia de seguridad de la base de datos principal, vuelva a habilitar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="b23b8-198">If you disabled the backup job on the principal database, reenable the job.</span></span>  
  
4.  <span data-ttu-id="b23b8-199">Si la base de datos necesita marcarse como de confianza después de una conmutación por error, es necesario realizar pasos adicionales de configuración después de iniciar la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="b23b8-199">If the database needs to be trustworthy after a failover, extra setup steps are necessary after mirroring begins.</span></span> <span data-ttu-id="b23b8-200">Para más información, consulte [Configurar una base de datos reflejada para usar la propiedad Trustworthy &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b23b8-200">For more information, see [Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b23b8-201">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="b23b8-201">Related Tasks</span></span>  
  
-   [<span data-ttu-id="b23b8-202">Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b23b8-202">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="b23b8-203">Restaurar una copia de seguridad de registros de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b23b8-203">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="b23b8-204">Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b23b8-204">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="b23b8-205">Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b23b8-205">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  
-   [<span data-ttu-id="b23b8-206">Establecer una base de datos reflejada cifrada</span><span class="sxs-lookup"><span data-stu-id="b23b8-206">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
-   [<span data-ttu-id="b23b8-207">Configurar una base de datos reflejada para usar la propiedad Trustworthy &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b23b8-207">Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;</span></span>](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="b23b8-208">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b23b8-208">See Also</span></span>  
 <span data-ttu-id="b23b8-209">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b23b8-209">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="b23b8-210">[Seguridad de transporte para la creación de reflejo de la base de datos y Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="b23b8-210">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="b23b8-211">[Configurar la creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b23b8-211">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="b23b8-212">[Realizar copias de seguridad de los catálogos de texto completo y restaurarlos](../../relational-databases/indexes/indexes.md) </span><span class="sxs-lookup"><span data-stu-id="b23b8-212">[Back Up and Restore Full-Text Catalogs and Indexes](../../relational-databases/indexes/indexes.md) </span></span>  
 <span data-ttu-id="b23b8-213">[Creación de reflejo de la base de datos y catálogos de texto completo &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b23b8-213">[Database Mirroring and Full-Text Catalogs &#40;SQL Server&#41;](database-mirroring-and-full-text-catalogs-sql-server.md) </span></span>  
 <span data-ttu-id="b23b8-214">[Replicación y creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b23b8-214">[Database Mirroring and Replication &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span></span>  
 <span data-ttu-id="b23b8-215">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b23b8-215">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="b23b8-216">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b23b8-216">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="b23b8-217">RESTORE &#40;argumentos, Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b23b8-217">RESTORE Arguments &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-arguments-transact-sql)  
  
  
