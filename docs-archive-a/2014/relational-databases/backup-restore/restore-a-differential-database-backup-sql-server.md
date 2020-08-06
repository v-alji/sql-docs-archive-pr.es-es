---
title: Restaurar una copia de seguridad diferencial de la base de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full differential backups [SQL Server]
- restoring databases [SQL Server], full differential backups
- database backups [SQL Server], full differential backups
- database restores [SQL Server], full differential backups
- backing up databases [SQL Server], full differential backups
ms.assetid: 0dd971a4-ee38-4dd3-9f30-ef77fc58dd11
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a8eab18d84efc1a990715e0d5488085252f93a7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675459"
---
# <a name="restore-a-differential-database-backup-sql-server"></a><span data-ttu-id="44296-102">Restaurar una copia de seguridad diferencial de la base de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="44296-102">Restore a Differential Database Backup (SQL Server)</span></span>
  <span data-ttu-id="44296-103">En este tema se describe cómo restaurar una copia de seguridad diferencial de la base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44296-103">This topic describes how to restore a differential database backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="44296-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="44296-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="44296-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="44296-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="44296-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="44296-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="44296-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="44296-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="44296-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="44296-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="44296-109">**Para restaurar una copia de seguridad diferencial de la base de datos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="44296-109">**To restore a differential database backup, using:**</span></span>  
  
     [<span data-ttu-id="44296-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="44296-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="44296-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="44296-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="44296-112">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="44296-112">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="44296-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="44296-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="44296-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="44296-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="44296-115">RESTORE no se permite en una transacción explícita o implícita.</span><span class="sxs-lookup"><span data-stu-id="44296-115">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="44296-116">Las copias de seguridad que se crean en una versión más reciente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se pueden restaurar en versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44296-116">Backups that are created by more recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be restored in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="44296-117">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], puede restaurar una base de datos de usuario a partir de una copia de seguridad de la base de datos creada utilizando [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="44296-117">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can restore a user database from a database backup that was created by using [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or a later version.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="44296-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="44296-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="44296-119">En el modelo de recuperación optimizado para cargas masivas de registros o completa, para poder restaurar una base de datos, se debe realizar una copia de seguridad del registro de transacciones activo (conocido como final del registro).</span><span class="sxs-lookup"><span data-stu-id="44296-119">Under the full or bulk-logged recovery model, before you can restore a database, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="44296-120">Para obtener más información, vea [Realizar copia de seguridad de un registro de transacciones &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="44296-120">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="44296-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="44296-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="44296-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="44296-122">Permissions</span></span>  
 <span data-ttu-id="44296-123">Si la base de datos que se va a restaurar no existe, el usuario debe tener permisos CREATE DATABASE para poder ejecutar RESTORE.</span><span class="sxs-lookup"><span data-stu-id="44296-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="44296-124">Si la base de datos existe, los permisos RESTORE corresponden de forma predeterminada a los miembros de los roles fijos de servidor **sysadmin** y **dbcreator** , y al propietario (**dbo**) de la base de datos (para la opción FROM DATABASE_SNAPSHOT, la base de datos siempre existe).</span><span class="sxs-lookup"><span data-stu-id="44296-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="44296-125">Los permisos RESTORE se conceden a los roles en los que la información acerca de la pertenencia está siempre disponible para el servidor.</span><span class="sxs-lookup"><span data-stu-id="44296-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="44296-126">Debido a que la pertenencia a un rol fijo de base de datos solo se puede comprobar cuando la base de datos es accesible y no está dañada, lo que no siempre ocurre cuando se ejecuta RESTORE, los miembros del rol fijo de base de datos **db_owner** no tienen permisos RESTORE.</span><span class="sxs-lookup"><span data-stu-id="44296-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="44296-127">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="44296-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-a-differential-database-backup"></a><span data-ttu-id="44296-128">Para restaurar una copia de seguridad diferencial de la base de datos</span><span class="sxs-lookup"><span data-stu-id="44296-128">To restore a differential database backup</span></span>  
  
1.  <span data-ttu-id="44296-129">Después de conectarse a la instancia adecuada de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol de servidores.</span><span class="sxs-lookup"><span data-stu-id="44296-129">After you connect to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="44296-130">Expanda **Bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="44296-130">Expand **Databases**.</span></span> <span data-ttu-id="44296-131">En función de la base de datos, seleccione una base de datos de usuario o expanda **Bases de datos del sistema**y, a continuación, seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="44296-131">Depending on the database, either select a user database or expand **System Databases**, and then select a system database.</span></span>  
  
3.  <span data-ttu-id="44296-132">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**, **Restaurar**y luego haga clic en **Base de datos**.</span><span class="sxs-lookup"><span data-stu-id="44296-132">Right-click the database, point to **Tasks**, point to **Restore**, and then click **Database**.</span></span>  
  
4.  <span data-ttu-id="44296-133">En la página **General** , use la sección **Origen** para especificar el origen y la ubicación de los conjuntos de copias de seguridad que se deben restaurar.</span><span class="sxs-lookup"><span data-stu-id="44296-133">On the **General** page, use the **Source** section to specify the source and location of the backup sets to restore.</span></span> <span data-ttu-id="44296-134">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="44296-134">Select one of the following options:</span></span>  
  
    -   <span data-ttu-id="44296-135">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="44296-135">**Database**</span></span>  
  
         <span data-ttu-id="44296-136">Seleccione la base de datos que desea restaurar en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="44296-136">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="44296-137">La lista solo contiene las bases de datos de las que se han realizado copias de seguridad de acuerdo con el historial de copias de seguridad de **msdb** .</span><span class="sxs-lookup"><span data-stu-id="44296-137">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="44296-138">Si la copia de seguridad se toma desde un servidor diferente, el servidor de destino no tendrá la información del historial de copia de seguridad de la base de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="44296-138">If the backup is taken from a different server, the destination server will not have the backup history information for the specified database.</span></span> <span data-ttu-id="44296-139">En este caso, seleccione **Dispositivo** para especificar manualmente el archivo o dispositivo que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="44296-139">In this case, select **Device** to manually specify the file or device to restore.</span></span>  
  
    -   <span data-ttu-id="44296-140">**Dispositivo**</span><span class="sxs-lookup"><span data-stu-id="44296-140">**Device**</span></span>  
  
         <span data-ttu-id="44296-141">Haga clic en el botón de exploración ( **...** ) para abrir el cuadro de diálogo **Seleccionar dispositivos de copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="44296-141">Click the browse (**...**) button to open the **Select backup devices** dialog box.</span></span> <span data-ttu-id="44296-142">En el cuadro **Tipo de medio de copia de seguridad** , seleccione uno de los tipos de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44296-142">In the **Backup media type** box, select one of the listed device types.</span></span> <span data-ttu-id="44296-143">Para seleccionar uno o varios dispositivos del cuadro **Medio de copia de seguridad** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="44296-143">To select one or more devices for the **Backup media** box, click **Add**.</span></span>  
  
         <span data-ttu-id="44296-144">Después de agregar los dispositivos que desee al cuadro de lista **Medio de copia de seguridad** , haga clic en **Aceptar** para volver a la página **General** .</span><span class="sxs-lookup"><span data-stu-id="44296-144">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
         <span data-ttu-id="44296-145">En el cuadro de lista **Origen: Dispositivo: Base de datos**, seleccione el nombre de la base de datos que se debe restaurar.</span><span class="sxs-lookup"><span data-stu-id="44296-145">In the **Source: Device: Database** list box, select the name of the database which should be restored.</span></span>  
  
         <span data-ttu-id="44296-146">**Nota** : esta lista solo está disponible cuando se selecciona **Dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="44296-146">**Note** This list is only available when **Device** is selected.</span></span> <span data-ttu-id="44296-147">Solo estarán disponibles las bases de datos que tienen copias de seguridad en el dispositivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="44296-147">Only databases that have backups on the selected device will be available.</span></span>  
  
5.  <span data-ttu-id="44296-148">En la sección **Destino** , el cuadro **Base de datos** se rellena automáticamente con el nombre de la base de datos que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="44296-148">In the **Destination** section, the **Database** box is automatically populated with the name of the database to be restored.</span></span> <span data-ttu-id="44296-149">Para cambiar el nombre de la base de datos, especifique el nuevo nombre en el cuadro **Base de datos** .</span><span class="sxs-lookup"><span data-stu-id="44296-149">To change the name of the database, enter the new name in the **Database** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="44296-150">Para detener la restauración en un momento dado específico, haga clic en **Escala de tiempo** para obtener acceso al cuadro de diálogo **Escala de tiempo de la copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="44296-150">To stop the restore at a specific point in time, click **Timeline** to access the **Backup Timeline** dialog box.</span></span> <span data-ttu-id="44296-151">Para obtener ayuda sobre cómo detener la restauración de una base de datos a un momento dado, consulte [Restaurar una base de datos de SQL Server a un momento dado &#40;modelo de recuperación completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="44296-151">For help with stopping a database restore at a specific point in time, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
6.  <span data-ttu-id="44296-152">En la cuadrícula **Conjuntos de copia de seguridad para restaurar** , seleccione las copias de seguridad mediante la copia de seguridad diferencial que desea restaurar.</span><span class="sxs-lookup"><span data-stu-id="44296-152">In the **Backup sets to restore** grid, select the backups through the differential backup that you wish to restore.</span></span>  
  
     <span data-ttu-id="44296-153">Para obtener información sobre las columnas de la cuadrícula **Conjuntos de copia de seguridad que se van a restaurar** , vea [Restaurar la base de datos &#40;página General&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)).</span><span class="sxs-lookup"><span data-stu-id="44296-153">For information about the columns in the **Backup sets to restore** grid, see [Restore Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
7.  <span data-ttu-id="44296-154">En la página **Opciones** , en el panel **Opciones de restauración** , puede seleccionar una de las opciones siguientes si son apropiadas para su situación:</span><span class="sxs-lookup"><span data-stu-id="44296-154">On the **Options** page, in the **Restore options** panel, you can select any of the following options, if appropriate for your situation:</span></span>  
  
    -   <span data-ttu-id="44296-155">**Sobrescribir la base de datos existente (WITH REPLACE)**</span><span class="sxs-lookup"><span data-stu-id="44296-155">**Overwrite the existing database (WITH REPLACE)**</span></span>  
  
    -   <span data-ttu-id="44296-156">**Conservar la configuración de replicación (WITH KEEP_REPLICATION)**</span><span class="sxs-lookup"><span data-stu-id="44296-156">**Preserve the replication settings (WITH KEEP_REPLICATION)**</span></span>  
  
    -   <span data-ttu-id="44296-157">**Preguntar antes de restaurar cada copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="44296-157">**Prompt before restoring each backup**</span></span>  
  
    -   <span data-ttu-id="44296-158">**Restringir el acceso a la base de datos restaurada (WITH RESTRICTED_USER)**</span><span class="sxs-lookup"><span data-stu-id="44296-158">**Restrict access to the restored database (WITH RESTRICTED_USER)**</span></span>  
  
     <span data-ttu-id="44296-159">Para obtener más información sobre estas opciones, vea [Restaurar base de datos &#40;página Opciones&#41;](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="44296-159">For more information about these options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
8.  <span data-ttu-id="44296-160">Seleccione una opción en el cuadro **Estado de recuperación** .</span><span class="sxs-lookup"><span data-stu-id="44296-160">Select an option for the **Recovery state** box.</span></span> <span data-ttu-id="44296-161">Este cuadro determina el estado de la base de datos después de la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="44296-161">This box determines the state of the database after the restore operation.</span></span>  
  
    -   <span data-ttu-id="44296-162">**RESTORE WITH RECOVERY** es el comportamiento predeterminado que deja la base de datos lista para usarse mediante la reversión de las transacciones no confirmadas.</span><span class="sxs-lookup"><span data-stu-id="44296-162">**RESTORE WITH RECOVERY** is the default behavior which leaves the database ready for use by rolling back the uncommitted transactions.</span></span> <span data-ttu-id="44296-163">No pueden restaurarse registros de transacciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="44296-163">Additional transaction logs cannot be restored.</span></span> <span data-ttu-id="44296-164">Seleccione esta opción si va a restaurar ahora todas las copias de seguridad necesarias.</span><span class="sxs-lookup"><span data-stu-id="44296-164">Select this option if you are restoring all of the necessary backups now.</span></span>  
  
    -   <span data-ttu-id="44296-165">**RESTORE WITH NORECOVERY** deja la base de datos no operativa y no revierte las transacciones no confirmadas.</span><span class="sxs-lookup"><span data-stu-id="44296-165">**RESTORE WITH NORECOVERY** which leaves the database non-operational, and does not roll back the uncommitted transactions.</span></span> <span data-ttu-id="44296-166">Pueden restaurarse registros de transacciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="44296-166">Additional transaction logs can be restored.</span></span> <span data-ttu-id="44296-167">La base de datos no puede se usar hasta que se recupera.</span><span class="sxs-lookup"><span data-stu-id="44296-167">The database cannot be used until it is recovered.</span></span>  
  
    -   <span data-ttu-id="44296-168">**RESTORE WITH STANDBY** deja la base de datos en modo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="44296-168">**RESTORE WITH STANDBY** which leaves the database in read-only mode.</span></span> <span data-ttu-id="44296-169">Deshace las transacciones sin confirmar, pero guarda las acciones de deshacer en un archivo en espera para que los efectos de la recuperación puedan revertirse.</span><span class="sxs-lookup"><span data-stu-id="44296-169">It undoes uncommitted transactions, but saves the undo actions in a standby file so that recovery effects can be reverted.</span></span>  
  
     <span data-ttu-id="44296-170">Para obtener descripciones de las opciones, consulte [Restaurar base de datos &#40;página Opciones&#41;](restore-database-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="44296-170">For descriptions of the options, see [Restore Database &#40;Options Page&#41;](restore-database-options-page.md).</span></span>  
  
9. <span data-ttu-id="44296-171">Habrá errores en las operaciones de restauración si hay conexiones activas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="44296-171">Restore operations will fail if there are active connections to the database.</span></span> <span data-ttu-id="44296-172">Active la opción **Cerrar conexiones existentes** para asegurarse de que se cierren todas las conexiones activas entre [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] y la base de datos.</span><span class="sxs-lookup"><span data-stu-id="44296-172">Check the **Close existing connections option** to ensure that all active connections between [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and the database are closed.</span></span>  
  
10. <span data-ttu-id="44296-173">Seleccione **Preguntar antes de restaurar cada copia de seguridad** si desea que se le pregunte en cada operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="44296-173">Select **Prompt before restoring each backup** if you wish to be prompted between each restore operation.</span></span> <span data-ttu-id="44296-174">No suele ser necesario a menos que la base de datos sea grande y desee supervisar el estado de la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="44296-174">This is not usually necessary unless the database is large and you wish to monitor the status of the restore operation.</span></span>  
  
11. <span data-ttu-id="44296-175">También puede usar la página **Archivos** para restaurar la base de datos a una nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="44296-175">Optionally, use the **Files** page to restore the database to a new location.</span></span> <span data-ttu-id="44296-176">Para obtener ayuda sobre cómo trasladar una base de datos, vea [Restaurar una base de datos a una nueva ubicación &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="44296-176">For help with moving a database, see [Restore a Database to a New Location &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md).</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="44296-177">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="44296-177">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-a-differential-database-backup"></a><span data-ttu-id="44296-178">Para restaurar una copia de seguridad diferencial de la base de datos</span><span class="sxs-lookup"><span data-stu-id="44296-178">To restore a differential database backup</span></span>  
  
1.  <span data-ttu-id="44296-179">Ejecute la instrucción RESTORE DATABASE con la cláusula NORECOVERY para restaurar la copia de seguridad de base de datos completa anterior a la copia de seguridad diferencial de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="44296-179">Execute the RESTORE DATABASE statement, specifying the NORECOVERY clause, to restore the full database backup that comes before the differential database backup.</span></span> <span data-ttu-id="44296-180">Para más información, vea: [Cómo: restaurar una copia de seguridad completa](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="44296-180">For more information, see [How to: Restore a Full Backup](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="44296-181">Ejecute la instrucción RESTORE DATABASE para restaurar la copia de seguridad diferencial de la base de datos especificando:</span><span class="sxs-lookup"><span data-stu-id="44296-181">Execute the RESTORE DATABASE statement to restore the differential database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="44296-182">El nombre de la base de datos a la que se aplicará la copia de seguridad diferencial de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="44296-182">The name of the database to which the differential database backup is applied.</span></span>  
  
    -   <span data-ttu-id="44296-183">El dispositivo de copia de seguridad desde el que se restaura la copia de seguridad diferencial de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="44296-183">The backup device where the differential database backup is restored from.</span></span>  
  
    -   <span data-ttu-id="44296-184">La cláusula NORECOVERY, si dispone de copias de seguridad del registro de transacciones que deban aplicarse después de que se restaure la copia de seguridad diferencial de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="44296-184">The NORECOVERY clause if you have transaction log backups to apply after the differential database backup is restored.</span></span> <span data-ttu-id="44296-185">En caso contrario, especifique la cláusula RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="44296-185">Otherwise, specify the RECOVERY clause.</span></span>  
  
3.  <span data-ttu-id="44296-186">Con el modelo de recuperación completa o modelo de recuperación optimizado para cargas masivas de registros, la restauración de una copia de seguridad diferencial de la base de datos restaura la base de datos hasta el momento en que se completó la copia de seguridad diferencial de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="44296-186">With the full or bulk-logged recovery model, restoring a differential database backup restores the database to the point at which the differential database backup was completed.</span></span> <span data-ttu-id="44296-187">Para recuperar hasta el momento del error, debe aplicar todas las copias de seguridad del registro de transacciones creadas después de la última copia de seguridad diferencial de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="44296-187">To recover to the point of failure, you must apply all transaction log backups created after the last differential database backup was created.</span></span> <span data-ttu-id="44296-188">Para obtener más información, vea [Aplicar copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="44296-188">For more information, see [Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="44296-189">Ejemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="44296-189">Examples (Transact-SQL)</span></span>  
  
#### <a name="a-restoring-a-differential-database-backup"></a><span data-ttu-id="44296-190">A.</span><span class="sxs-lookup"><span data-stu-id="44296-190">A.</span></span> <span data-ttu-id="44296-191">Restaurar una copia de seguridad diferencial de la base de datos</span><span class="sxs-lookup"><span data-stu-id="44296-191">Restoring a differential database backup</span></span>  
 <span data-ttu-id="44296-192">En este ejemplo se restaura una copia de seguridad completa y una copia de seguridad diferencial de la base de datos `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="44296-192">This example restores a database and differential database backup of the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Assume the database is lost, and restore full database,   
-- specifying the original full database backup and NORECOVERY,   
-- which allows subsequent restore operations to proceed.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH NORECOVERY;  
GO  
-- Now restore the differential database backup, the second backup on   
-- the MyAdvWorks_1 backup device.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH FILE = 2,  
   RECOVERY;  
GO  
```  
  
#### <a name="b-restoring-a-database-differential-database-and-transaction-log-backup"></a><span data-ttu-id="44296-193">B.</span><span class="sxs-lookup"><span data-stu-id="44296-193">B.</span></span> <span data-ttu-id="44296-194">Restaurar una base de datos, una base de datos diferencial y una copia de seguridad del registro de transacciones</span><span class="sxs-lookup"><span data-stu-id="44296-194">Restoring a database, differential database, and transaction log backup</span></span>  
 <span data-ttu-id="44296-195">En este ejemplo se restaura una copia de seguridad completa, una copia de seguridad diferencial y una copia de seguridad del registro de transacciones de la base de datos `MyAdvWorks` .</span><span class="sxs-lookup"><span data-stu-id="44296-195">This example restores a database, differential database, and transaction log backup of the `MyAdvWorks` database.</span></span>  
  
```sql  
-- Assume the database is lost at this point. Now restore the full   
-- database. Specify the original full database backup and NORECOVERY.  
-- NORECOVERY allows subsequent restore operations to proceed.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH NORECOVERY;  
GO  
-- Now restore the differential database backup, the second backup on   
-- the MyAdvWorks_1 backup device.  
RESTORE DATABASE MyAdvWorks  
   FROM MyAdvWorks_1  
   WITH FILE = 2,  
   NORECOVERY;  
GO  
-- Now restore each transaction log backup created after  
-- the differential database backup.  
RESTORE LOG MyAdvWorks  
   FROM MyAdvWorks_log1  
   WITH NORECOVERY;  
GO  
RESTORE LOG MyAdvWorks  
   FROM MyAdvWorks_log2  
   WITH RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="44296-196">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="44296-196">Related Tasks</span></span>  
  
-   [<span data-ttu-id="44296-197">Crear una copia de seguridad diferencial de una base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="44296-197">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="44296-198">Restaurar una copia de seguridad de registros de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="44296-198">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="44296-199">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44296-199">See Also</span></span>  
 <span data-ttu-id="44296-200">[Copias de seguridad diferenciales &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="44296-200">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="44296-201">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="44296-201">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
