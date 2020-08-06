---
title: Realizar una copia de seguridad del registro de transacciones cuando la base de datos está dañada (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], damaged
- backing up [SQL Server]. damaged database
- transaction log backups [SQL Server], damaged databases
ms.assetid: 9b8873cc-df54-4336-ab9b-8f525132c2b0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea712e6bc4e73119a4f07a7775f9f25e212f8534
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662118"
---
# <a name="back-up-the-transaction-log-when-the-database-is-damaged-sql-server"></a><span data-ttu-id="71641-102">Realizar una copia de seguridad del registro de transacciones cuando la base de datos está dañada (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="71641-102">Back Up the Transaction Log When the Database Is Damaged (SQL Server)</span></span>
  <span data-ttu-id="71641-103">En este tema se describe cómo realizar la copia de seguridad de un registro de transacciones cuando la base de datos está dañada en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71641-103">This topic describes how to back up a transaction log when the database is damaged in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="71641-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="71641-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="71641-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="71641-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="71641-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="71641-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="71641-107">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="71641-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="71641-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="71641-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="71641-109">**Para realizar una copia de seguridad del registro de transacciones cuando la base de datos está dañada, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="71641-109">**To back up the transaction log when the database is damaged, using:**</span></span>  
  
     [<span data-ttu-id="71641-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="71641-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="71641-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="71641-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="71641-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="71641-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="71641-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="71641-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="71641-114">La instrucción BACKUP no se permite en una transacción explícita o implícita.</span><span class="sxs-lookup"><span data-stu-id="71641-114">The BACKUP statement is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="71641-115">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="71641-115">Recommendations</span></span>  
  
-   <span data-ttu-id="71641-116">En una base de datos que utiliza el modelo de recuperación completo u optimizado para cargas masivas de registros, generalmente es necesario hacer una copia del final del registro antes de empezar a restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="71641-116">For a database that uses either the full or bulk-logged recovery model, you generally need to back up the tail of the log before beginning to restore the database.</span></span> <span data-ttu-id="71641-117">También debería hacer una copia del final del registro de la base de datos principal antes de conmutar por error a una configuración de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="71641-117">You also should back up the tail of the log of the primary database before failing over a log shipping configuration.</span></span> <span data-ttu-id="71641-118">Al restaurar la copia del final del registro como última copia de seguridad de registros antes de recuperar la base de datos, se evita perder el trabajo después de que se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="71641-118">Restoring the tail-log backup as the final log backup before recovering the database avoids work loss after a failure.</span></span> <span data-ttu-id="71641-119">Para obtener más información sobre las copias del final del registro, vea [Copias del final del registro &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="71641-119">For more information about tail-log backups, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="71641-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="71641-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="71641-121">Permisos</span><span class="sxs-lookup"><span data-stu-id="71641-121">Permissions</span></span>  
 <span data-ttu-id="71641-122">De forma predeterminada, los permisos BACKUP DATABASE y BACKUP LOG corresponden a los miembros del rol fijo de servidor **sysadmin** y de los roles fijos de base de datos **db_owner** y **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="71641-122">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="71641-123">Los problemas de propiedad y permisos del archivo físico del dispositivo de copia de seguridad pueden interferir con una operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="71641-123">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="71641-124">debe poder leer y escribir en el dispositivo y la cuenta en la que se ejecuta el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe tener permisos de escritura.</span><span class="sxs-lookup"><span data-stu-id="71641-124">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="71641-125">En cambio, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que agrega una entrada para un dispositivo de copia de seguridad en las tablas del sistema, no comprueba los permisos de acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="71641-125">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="71641-126">Es posible que estos problemas con el archivo físico del dispositivo de copia de seguridad no aparezcan hasta que se tenga acceso al recurso físico, al intentar la copia de seguridad o la restauración.</span><span class="sxs-lookup"><span data-stu-id="71641-126">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="71641-127">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="71641-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-back-up-the-tail-of-the-transaction-log"></a><span data-ttu-id="71641-128">Para hacer una copia del final registro de transacciones</span><span class="sxs-lookup"><span data-stu-id="71641-128">To back up the tail of the transaction log</span></span>  
  
1.  <span data-ttu-id="71641-129">Después de conectarse a la instancia apropiada de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol correspondiente.</span><span class="sxs-lookup"><span data-stu-id="71641-129">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="71641-130">Expanda **Bases de datos**y, en función de la base de datos, seleccione la base de datos de un usuario o expanda **Bases de datos del sistema** y seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="71641-130">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="71641-131">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y haga clic en **Copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="71641-131">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="71641-132">Aparece el cuadro de diálogo **Copia de seguridad de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="71641-132">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="71641-133">En el cuadro de lista **Base de datos** , compruebe el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="71641-133">In the **Database** list box, verify the database name.</span></span> <span data-ttu-id="71641-134">También puede seleccionar otra base de datos en la lista.</span><span class="sxs-lookup"><span data-stu-id="71641-134">You can optionally select a different database from the list.</span></span>  
  
5.  <span data-ttu-id="71641-135">Compruebe que el modelo de recuperación sea **FULL** o **BULK_LOGGED**.</span><span class="sxs-lookup"><span data-stu-id="71641-135">Verify that the recovery model is either **FULL** or **BULK_LOGGED**.</span></span>  
  
6.  <span data-ttu-id="71641-136">En el cuadro de lista **Tipo de copia de seguridad** , seleccione **Registro de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="71641-136">In the **Backup type** list box, select **Transaction Log**.</span></span>  
  
7.  <span data-ttu-id="71641-137">Anule la selección de la opción **Copia de seguridad de solo copia** .</span><span class="sxs-lookup"><span data-stu-id="71641-137">Leave **Copy Only Backup** deselected.</span></span>  
  
8.  <span data-ttu-id="71641-138">En el área **Conjunto de copia de seguridad** , acepte el nombre del conjunto de copia de seguridad predeterminado sugerido en el cuadro de texto **Nombre** o especifique otro nombre.</span><span class="sxs-lookup"><span data-stu-id="71641-138">In the **Backup set** area, either accept the default backup set name suggested in the **Name** text box, or enter a different name for the backup set.</span></span>  
  
9. <span data-ttu-id="71641-139">En el cuadro de texto **Descripción** , escriba una descripción para la copia del final del registro.</span><span class="sxs-lookup"><span data-stu-id="71641-139">In the **Description** text box, enter a description for the tail-log backup.</span></span>  
  
10. <span data-ttu-id="71641-140">Especifique cuándo expirará el conjunto de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="71641-140">Specify when the backup set will expire:</span></span>  
  
    -   <span data-ttu-id="71641-141">Para que el conjunto de copia de seguridad expire al cabo de un número de días específico, haga clic en **Después de** (opción predeterminada) y escriba el número de días tras la creación del conjunto en que este expirará.</span><span class="sxs-lookup"><span data-stu-id="71641-141">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="71641-142">Este valor puede estar entre 0 y 99999 días; el valor 0 significa que el conjunto de copia de seguridad no expirará nunca.</span><span class="sxs-lookup"><span data-stu-id="71641-142">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="71641-143">El valor predeterminado se establece en la opción **Tiempo predeterminado de retención de medios de copia de seguridad (días)** del cuadro de diálogo **Propiedades del servidor** (página**Configuración de base de datos** ).</span><span class="sxs-lookup"><span data-stu-id="71641-143">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="71641-144">Para tener acceso a este cuadro de diálogo, haga clic con el botón derecho en el nombre del servidor en el Explorador de objetos y seleccione Propiedades. Después, seleccione la página **Configuración de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="71641-144">To access this dialog box, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="71641-145">Para que el conjunto de copia de seguridad expire en una determinada fecha, haga clic en **El**y escriba la fecha en la que expirará.</span><span class="sxs-lookup"><span data-stu-id="71641-145">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
11. <span data-ttu-id="71641-146">Elija el tipo de destino de la copia de seguridad haciendo clic en **Disco** o **Cinta**.</span><span class="sxs-lookup"><span data-stu-id="71641-146">Choose the type of backup destination by clicking **Disk** or **Tape**.</span></span> <span data-ttu-id="71641-147">Para seleccionar las rutas de acceso de hasta 64 unidades de disco o cinta que contienen un solo conjunto de medios, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="71641-147">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span> <span data-ttu-id="71641-148">Las rutas seleccionadas se muestran en el cuadro de lista **Copia de seguridad en** .</span><span class="sxs-lookup"><span data-stu-id="71641-148">The selected paths are displayed in the **Backup to** list box.</span></span>  
  
     <span data-ttu-id="71641-149">Para eliminar un destino de copia de seguridad, selecciónelo y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="71641-149">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="71641-150">Para ver el contenido de un destino de copia de seguridad, selecciónelo y haga clic en **Contenido**.</span><span class="sxs-lookup"><span data-stu-id="71641-150">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
12. <span data-ttu-id="71641-151">En la página **Opciones** , seleccione una opción de **Sobrescribir medios** haciendo clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="71641-151">On the **Options** page, select an **Overwrite Media** option, by clicking one of the following:</span></span>  
  
    -   <span data-ttu-id="71641-152">**Hacer copia de seguridad en el conjunto de medios existente**</span><span class="sxs-lookup"><span data-stu-id="71641-152">**Back up to the existing media set**</span></span>  
  
         <span data-ttu-id="71641-153">Para esta opción, haga clic en **Anexar al conjunto de copia de seguridad existente** o **Sobrescribir todos los conjuntos de copia de seguridad existentes**.</span><span class="sxs-lookup"><span data-stu-id="71641-153">For this option, click either **Append to the existing backup set** or **Overwrite all existing backup sets**.</span></span>  
  
         <span data-ttu-id="71641-154">Opcionalmente, seleccione **Comprobar nombre de conjunto de medios y fecha de expiración del conjunto de copia de seguridad** para que la operación de copia de seguridad compruebe la fecha y la hora en que expiran el conjunto de medios y el conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="71641-154">Optionally, select **Check media set name and backup set expiration** to cause the backup operation to verify the date and time at which the media set and backup set expire.</span></span>  
  
         <span data-ttu-id="71641-155">También puede escribir un nombre en el cuadro de texto **Nombre del conjunto de medios** .</span><span class="sxs-lookup"><span data-stu-id="71641-155">Optionally, enter a name in the **Media set name** text box.</span></span> <span data-ttu-id="71641-156">Si no especifica ningún nombre, se creará un conjunto de medios con un nombre en blanco.</span><span class="sxs-lookup"><span data-stu-id="71641-156">If no name is specified, a media set with a blank name is created.</span></span> <span data-ttu-id="71641-157">Si especifica un nombre para el conjunto, los medios (cinta o disco) se comprueban para ver si el nombre real coincide con el nombre especificado aquí.</span><span class="sxs-lookup"><span data-stu-id="71641-157">If you specify a media set name, the media (tape or disk) is checked to see whether the actual name matches the name you enter here.</span></span>  
  
         <span data-ttu-id="71641-158">Si deja el nombre del conjunto de medios en blanco y selecciona la casilla para comprobarlo con los medios, el resultado correcto significará que el nombre del conjunto en los medios también está en blanco.</span><span class="sxs-lookup"><span data-stu-id="71641-158">If you leave the media name blank and check the box to check it against the media, success will equal the media name on the media also being blank.</span></span>  
  
    -   <span data-ttu-id="71641-159">**Hacer copia de seguridad en un nuevo conjunto de medios y borrar todos los conjuntos de copia de seguridad existentes**</span><span class="sxs-lookup"><span data-stu-id="71641-159">**Back up to a new media set, and erase all existing backup sets**</span></span>  
  
         <span data-ttu-id="71641-160">Para esta opción, especifique un nombre en el cuadro de texto **Nuevo nombre del conjunto de medios** y, si lo desea, describa el conjunto de medios en el cuadro de texto **Nueva descripción del conjunto de medios** .</span><span class="sxs-lookup"><span data-stu-id="71641-160">For this option, enter a name in the **New media set name** text box, and, optionally, describe the media set in the **New media set description** text box.</span></span>  
  
     <span data-ttu-id="71641-161">Para obtener más información sobre los conjuntos de medios, vea [Conjuntos de medios, familias de medios y conjuntos de copias de seguridad &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="71641-161">For more information about media set options, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
13. <span data-ttu-id="71641-162">Opcionalmente, en la sección **Confiabilidad** , seleccione:</span><span class="sxs-lookup"><span data-stu-id="71641-162">In the **Reliability** section, optionally, check:</span></span>  
  
    -   <span data-ttu-id="71641-163">**Comprobar copia de seguridad al finalizar**.</span><span class="sxs-lookup"><span data-stu-id="71641-163">**Verify backup when finished**.</span></span>  
  
    -   <span data-ttu-id="71641-164">**Realizar suma de comprobación antes de escribir en los medios**.</span><span class="sxs-lookup"><span data-stu-id="71641-164">**Perform checksum before writing to media**.</span></span>  
  
    -   <span data-ttu-id="71641-165">**Continuar después de un error de suma de comprobación**</span><span class="sxs-lookup"><span data-stu-id="71641-165">**Continue on checksum error**</span></span>  
  
     <span data-ttu-id="71641-166">Para obtener más información sobre las sumas de comprobación, vea [Errores posibles de medios durante copia de seguridad y restauración &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="71641-166">For information on checksums, see [Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md).</span></span>  
  
14. <span data-ttu-id="71641-167">En la sección **Registro de transacciones** , active **Realizar copia del final del registro y dejar la base de datos en estado de restauración**.</span><span class="sxs-lookup"><span data-stu-id="71641-167">In the **Transaction log** section, check **Back up the tail of the log, and leave database in the restoring state**.</span></span>  
  
     <span data-ttu-id="71641-168">Esto es equivalente a especificar la instrucción [BACKUP](/sql/t-sql/statements/backup-transact-sql) siguiente:</span><span class="sxs-lookup"><span data-stu-id="71641-168">This is equivalent to specifying the following [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement:</span></span>  
  
     `BACKUP LOG <database_name> TO <backup_device> WITH NORECOVERY`  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="71641-169">En el momento de la restauración, el cuadro de diálogo Restaurar base de datos muestra el tipo de una copia del final del registro como **Registro de transacciones (solo copia)** .</span><span class="sxs-lookup"><span data-stu-id="71641-169">At restore time, the Restore Database dialog box displays the type of a tail-log backup as **Transaction Log (Copy Only)**.</span></span>  
  
15. <span data-ttu-id="71641-170">Si va a realizar copias de seguridad en una unidad de cinta (según se haya especificado en la sección **Destino** de la página **General** ), la opción **Descargar la cinta después de realizar la copia de seguridad** está activa.</span><span class="sxs-lookup"><span data-stu-id="71641-170">If you are backing up to a tape drive (as specified in the **Destination** section of the **General** page), the **Unload the tape after backup** option is active.</span></span> <span data-ttu-id="71641-171">Al hacer clic en esta opción se activa la opción **Rebobinar la cinta antes de descargar** .</span><span class="sxs-lookup"><span data-stu-id="71641-171">Clicking this option activates the **Rewind the tape before unloading** option.</span></span>  
  
16. [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="71641-172">y las versiones posteriores admiten la [compresión de copia de seguridad](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="71641-172">and later supports [backup compression](backup-compression-sql-server.md).</span></span> <span data-ttu-id="71641-173">De forma predeterminada, el hecho de que se comprima una copia de seguridad depende del valor de la opción de configuración del servidor **backup-compression default** .</span><span class="sxs-lookup"><span data-stu-id="71641-173">By default, whether a backup is compressed depends on the value of the **backup-compression default** server configuration option.</span></span> <span data-ttu-id="71641-174">Pero, independientemente del valor predeterminado actual de nivel de servidor, puede comprimir una copia de seguridad si activa **Comprimir copia de seguridad**e impedir la compresión si activa **No comprimir copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="71641-174">However, regardless of the current server-level default, you can compress a backup by checking **Compress backup**, and you can prevent compression by checking **Do not compress backup**.</span></span>  
  
     <span data-ttu-id="71641-175">**Para ver el valor predeterminado actual de la compresión de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="71641-175">**To view the current backup compression default**</span></span>  
  
    -   [<span data-ttu-id="71641-176">Ver o establecer la opción de configuración del servidor de compresión de copia de seguridad predeterminada</span><span class="sxs-lookup"><span data-stu-id="71641-176">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="71641-177">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="71641-177">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-backup-of-the-currently-active-transaction-log"></a><span data-ttu-id="71641-178">Para crear una copia de seguridad del registro de transacciones activo</span><span class="sxs-lookup"><span data-stu-id="71641-178">To create a backup of the currently active transaction log</span></span>  
  
1.  <span data-ttu-id="71641-179">Ejecute la instrucción BACKUP LOG para realizar una copia de seguridad del registro de transacciones activo especificando:</span><span class="sxs-lookup"><span data-stu-id="71641-179">Execute the BACKUP LOG statement to back up the currently active transaction log, specifying:</span></span>  
  
    -   <span data-ttu-id="71641-180">El nombre de la base de datos a la que pertenece el registro de transacciones del que se va a hacer una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="71641-180">The name of the database to which the transaction log to back up belongs.</span></span>  
  
    -   <span data-ttu-id="71641-181">El dispositivo de copia de seguridad en el que se va a escribir la copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="71641-181">The backup device where the transaction log backup will be written.</span></span>  
  
    -   <span data-ttu-id="71641-182">La cláusula NO_TRUNCATE.</span><span class="sxs-lookup"><span data-stu-id="71641-182">The NO_TRUNCATE clause.</span></span>  
  
         <span data-ttu-id="71641-183">Esta cláusula permite realizar una copia de seguridad de la parte activa del registro de transacciones aunque no se tenga acceso a la base de datos, siempre y cuando se pueda tener acceso al archivo del registro de transacciones y éste no esté dañado.</span><span class="sxs-lookup"><span data-stu-id="71641-183">This clause allows the active part of the transaction log to be backed up even if the database is inaccessible, provided that the transaction log file is accessible and undamaged.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="71641-184">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="71641-184">Example (Transact-SQL)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71641-185">En este ejemplo se utiliza [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], que usa el modelo de recuperación simple.</span><span class="sxs-lookup"><span data-stu-id="71641-185">This example uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], which uses the simple recovery model.</span></span> <span data-ttu-id="71641-186">Con el fin de permitir copias de seguridad de registros, antes de realizar una copia de seguridad completa de la base de datos, la base de datos se ha configurado para usar el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="71641-186">To permit log backups, before taking a full database backup, the database was set to use the full recovery model.</span></span> <span data-ttu-id="71641-187">Para obtener más información, vea [Ver o cambiar el modelo de recuperación de una base de datos &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="71641-187">For more information, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="71641-188">En este ejemplo se realiza el registro de transacciones actualmente activo cuando una base de datos está dañada e inaccesible, si el registro de transacciones no está dañado y está accesible.</span><span class="sxs-lookup"><span data-stu-id="71641-188">This example backs up the currently active transaction log when a database is damaged and inaccessible, if the transaction log is undamaged and accessible.</span></span>  
  
```scr  
BACKUP LOG AdventureWorks2012  
   TO MyAdvWorks_FullRM_log1  
   WITH NO_TRUNCATE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="71641-189">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71641-189">See Also</span></span>  
 <span data-ttu-id="71641-190">[Restaurar una copia de seguridad del registro de transacciones &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="71641-190">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 <span data-ttu-id="71641-191">[Restaurar una base de datos de SQL Server a un momento dado &#40;modelo de recuperación completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="71641-191">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 <span data-ttu-id="71641-192">[Copia de seguridad de la base de datos &#40;página Opciones de copia de seguridad&#41;](back-up-database-backup-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="71641-192">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) </span></span>  
 <span data-ttu-id="71641-193">[Copia de seguridad de base de datos &#40;página General&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="71641-193">[Back Up Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="71641-194">[Aplicar copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="71641-194">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="71641-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="71641-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="71641-196">[Restauraciones de archivos &#40;modelo de recuperación simple&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="71641-196">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="71641-197">Restauraciones de archivos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="71641-197">File Restores &#40;Full Recovery Model&#41;</span></span>](file-restores-full-recovery-model.md)  
  
  
