---
title: Revertir una base de datos a una instantánea de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], reverting to
- reverting databases
ms.assetid: 8f74dd31-c9ca-4537-8760-0c7648f0787d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1c78da3d7c559309c0563760e7062f01cf784648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672087"
---
# <a name="revert-a-database-to-a-database-snapshot"></a><span data-ttu-id="7a02a-102">Revertir una base de datos a una instantánea de base de datos</span><span class="sxs-lookup"><span data-stu-id="7a02a-102">Revert a Database to a Database Snapshot</span></span>
  <span data-ttu-id="7a02a-103">Si se dañan los datos de una base de datos en línea, revertir la base de datos a una instantánea de base de datos anterior puede ser, en algunos casos, ser una alternativa adecuada a restaurar la base de datos a partir de una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7a02a-103">If data in an online database becomes damaged, in some cases, reverting the database to a database snapshot that predates the damage might be an appropriate alternative to restoring the database from a backup.</span></span> <span data-ttu-id="7a02a-104">Por ejemplo, revertir una base de datos puede resultar útil para revertir un error grave del usuario que sea reciente, por ejemplo la eliminación de una tabla.</span><span class="sxs-lookup"><span data-stu-id="7a02a-104">For example, reverting a database might be useful for reverse a recent serious user error, such as a dropped table.</span></span> <span data-ttu-id="7a02a-105">Tenga en cuenta que se pierden todos los cambios realizados después de que se creara la instantánea.</span><span class="sxs-lookup"><span data-stu-id="7a02a-105">However, all changes made after the snapshot was created are lost.</span></span>  
  
-   <span data-ttu-id="7a02a-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="7a02a-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7a02a-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7a02a-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7a02a-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7a02a-108">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="7a02a-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7a02a-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7a02a-110">**Para revertir una base de datos a una instantánea de base de datos, con:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="7a02a-110">**To Revert a Database to a Database Snapshot, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7a02a-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="7a02a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7a02a-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7a02a-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="7a02a-113">La reversión no se admite en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="7a02a-113">Reverting is unsupported under the following conditions:</span></span>  
  
-   <span data-ttu-id="7a02a-114">La base de datos debe tener en ese momento solo una instantánea de base de datos, a la que se va a revertir.</span><span class="sxs-lookup"><span data-stu-id="7a02a-114">The database must currently have only one database snapshot, to which you plan to revert.</span></span>  
  
-   <span data-ttu-id="7a02a-115">La base de datos contiene grupos de archivos de solo lectura o comprimidos.</span><span class="sxs-lookup"><span data-stu-id="7a02a-115">Any read-only or compressed filegroups exist in the database.</span></span>  
  
-   <span data-ttu-id="7a02a-116">Algunos archivos que están ahora sin conexión estaban en línea cuando se creó la instantánea.</span><span class="sxs-lookup"><span data-stu-id="7a02a-116">Any files are now offline but were online when the snapshot was created.</span></span>  
  
 <span data-ttu-id="7a02a-117">Antes de revertir a una base de datos, debe tener en cuenta los siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="7a02a-117">Before reverting a database, consider the following limitations:</span></span>  
  
-   <span data-ttu-id="7a02a-118">La reversión no se utiliza para la recuperación de medios.</span><span class="sxs-lookup"><span data-stu-id="7a02a-118">Reverting is not intended for media recovery.</span></span> <span data-ttu-id="7a02a-119">.</span><span class="sxs-lookup"><span data-stu-id="7a02a-119">.</span></span> <span data-ttu-id="7a02a-120">Una instantánea de base de datos es una copia incompleta de los archivos de base de datos, de modo que si se daña la base de datos o la instantánea de base de datos, es probable que no se pueda revertir a partir de una instantánea.</span><span class="sxs-lookup"><span data-stu-id="7a02a-120">A database snapshot is an incomplete copy of the database files, so if either the database or the database snapshot is corrupted, reverting from a snapshot is likely to be impossible.</span></span> <span data-ttu-id="7a02a-121">Además, aunque sea posible, no es probable que la reversión corrija el problema si se produjesen daños.</span><span class="sxs-lookup"><span data-stu-id="7a02a-121">Furthermore, even when it is possible, reverting in the event of corruption is unlikely to correct the problem.</span></span> <span data-ttu-id="7a02a-122">Por lo tanto, para proteger una base de datos es esencial hacer copias de seguridad con regularidad y probar el plan de restauración.</span><span class="sxs-lookup"><span data-stu-id="7a02a-122">Therefore, taking regular backups and testing your restore plan are essential to protect a database.</span></span> <span data-ttu-id="7a02a-123">Para obtener más información, consulte [Realizar copias de seguridad y restaurar bases de datos de SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="7a02a-123">For more information, see [Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7a02a-124">Si tiene que restaurar la base de datos de origen al momento en que creó una instantánea de base de datos, use el modelo de recuperación completa e implemente una directiva de copia de seguridad que le habilite para ello.</span><span class="sxs-lookup"><span data-stu-id="7a02a-124">If you need to be able to restore the source database to the point in time at which you created a database snapshot, use the full recovery model and implement a backup policy that enables you to do that.</span></span>  
  
-   <span data-ttu-id="7a02a-125">La base de datos revertida sobrescribe la base de datos de origen original, de modo que se pierden todos los cambios realizados en la base de datos desde que se creó la instantánea.</span><span class="sxs-lookup"><span data-stu-id="7a02a-125">The original source database is overwritten by the reverted database, so any updates to the database since the snapshot's creation are lost.</span></span>  
  
-   <span data-ttu-id="7a02a-126">La operación de reversión sobrescribe también el archivo de registro antiguo y lo vuelve a crear.</span><span class="sxs-lookup"><span data-stu-id="7a02a-126">The revert operation also overwrites the old log file and rebuilds the log.</span></span> <span data-ttu-id="7a02a-127">Por consiguiente, la base de datos revertida no se puede poner al día en el punto de error del usuario.</span><span class="sxs-lookup"><span data-stu-id="7a02a-127">Consequently, you cannot roll the reverted database forward to the point of user error.</span></span> <span data-ttu-id="7a02a-128">Por esta razón, recomendamos realizar una copia de seguridad del registro antes de revertir una base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a02a-128">Therefore, we recommend that you back up the log before reverting a database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7a02a-129">Aunque no puede restaurar el registro original para poner al día la base de datos, la información del archivo de registro original puede ser útil para reconstruir los datos perdidos.</span><span class="sxs-lookup"><span data-stu-id="7a02a-129">Although you cannot restore the original log to roll forward the database, the information in the original log file can be useful for reconstructing lost data.</span></span>  
  
-   <span data-ttu-id="7a02a-130">La reversión interrumpe la cadena de copias de seguridad del registro.</span><span class="sxs-lookup"><span data-stu-id="7a02a-130">Reverting breaks the log backup chain.</span></span> <span data-ttu-id="7a02a-131">Así pues, antes de utilizar copias de seguridad de registros de la base de datos revertida, primero deberá realizar una copia de seguridad completa de la base de datos o una copia de seguridad de los archivos.</span><span class="sxs-lookup"><span data-stu-id="7a02a-131">Therefore, before you can take log backups of the reverted database, you must first take a full database backup or file backup.</span></span> <span data-ttu-id="7a02a-132">Recomendamos realizar una copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a02a-132">We recommend a full database backup.</span></span>  
  
-   <span data-ttu-id="7a02a-133">Durante una operación de reversión, tanto la instantánea como la base de datos de origen no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="7a02a-133">During a revert operation, both the snapshot and the source database are unavailable.</span></span> <span data-ttu-id="7a02a-134">La base de datos de origen y la instantánea se marcan como "En restauración".</span><span class="sxs-lookup"><span data-stu-id="7a02a-134">The source database and snapshot are both marked "In restore."</span></span> <span data-ttu-id="7a02a-135">Si se produce un error durante la operación de reversión, cuando la base de datos se inicie de nuevo, la operación de reversión intentará finalizar la reversión.</span><span class="sxs-lookup"><span data-stu-id="7a02a-135">If an error occurs during the revert operation, when the database starts up again, the revert operation will try to finish reverting.</span></span>  
  
-   <span data-ttu-id="7a02a-136">Los metadatos de una base de datos revertida son los mismos que los metadatos del momento de realizar la instantánea.</span><span class="sxs-lookup"><span data-stu-id="7a02a-136">The metadata of a reverted database is the same as the metadata at the time of the snapshot.</span></span>  
  
-   <span data-ttu-id="7a02a-137">Al revertir se quitan todos los catálogos de texto completo.</span><span class="sxs-lookup"><span data-stu-id="7a02a-137">Reverting drops all the full-text catalogs.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="7a02a-138">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7a02a-138">Prerequisites</span></span>  
 <span data-ttu-id="7a02a-139">Asegúrese de que la base de datos de origen y la instantánea de base de datos cumplen los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="7a02a-139">Ensure that the source database and database snapshot meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="7a02a-140">Compruebe que no se ha dañado la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a02a-140">Verify that the database has not become corrupted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7a02a-141">Si se ha dañado la base de datos, tendrá que restaurarla a partir de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7a02a-141">If the database has been corrupted, you will need to restore it from backups.</span></span> <span data-ttu-id="7a02a-142">Para obtener más información, vea [Restauraciones de base de datos completas &#40;modelo de recuperación simple&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) o [Restauraciones de base de datos completas &#40;modelo de recuperación completa&#41;](../backup-restore/complete-database-restores-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="7a02a-142">For more information, see [Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) or [Complete Database Restores &#40;Full Recovery Model&#41;](../backup-restore/complete-database-restores-full-recovery-model.md).</span></span>  
  
-   <span data-ttu-id="7a02a-143">Identifique una instantánea reciente creada antes del error.</span><span class="sxs-lookup"><span data-stu-id="7a02a-143">Identify a recent snapshot that was created before the error.</span></span> <span data-ttu-id="7a02a-144">Para obtener más información, vea [Ver una instantánea de base de datos &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7a02a-144">For more information, see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span></span>  
  
-   <span data-ttu-id="7a02a-145">Quite cualquier otra instantánea que exista actualmente en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a02a-145">Drop any other snapshots that currently exist on the database.</span></span> <span data-ttu-id="7a02a-146">Para obtener más información, vea [Eliminar una instantánea de base de datos &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7a02a-146">For more information, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7a02a-147">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7a02a-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7a02a-148">Permisos</span><span class="sxs-lookup"><span data-stu-id="7a02a-148">Permissions</span></span>  
 <span data-ttu-id="7a02a-149">Cualquier usuario que tenga permisos de RESTORE DATABASE en la base de datos de origen puede revertirla a su estado cuando se creó una instantánea de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a02a-149">Any user who has RESTORE DATABASE permissions on the source database can revert it to its state when a database snapshot was created.</span></span>  
  
##  <a name="how-to-revert-a-database-to-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7a02a-150">Revertir una base de datos a una instantánea de base de datos (utilizando Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7a02a-150">How to Revert a Database to a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="7a02a-151">**Para revertir una base de datos a una instantánea de base de datos**</span><span class="sxs-lookup"><span data-stu-id="7a02a-151">**To revert a database to a database snapshot**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a02a-152">Para obtener un ejemplo de este procedimiento, vea [Ejemplos (Transact-SQL)](#TsqlExample), más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="7a02a-152">For an example of this procedure, see [Examples (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="7a02a-153">Identifique la instantánea de base de datos a la que desea revertir la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a02a-153">Identify the database snapshot to which you want to revert the database.</span></span> <span data-ttu-id="7a02a-154">Puede ver las instantáneas en una base de datos en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (vea [Ver una instantánea de base de datos &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="7a02a-154">You can view the snapshots on a database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md)).</span></span> <span data-ttu-id="7a02a-155">Además, puede identificar la base de datos de origen de una vista a partir de la columna **source_database_id** de la vista de catálogo [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="7a02a-155">Also, you can identify the source database of a view from the **source_database_id** column of the [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view.</span></span>  
  
2.  <span data-ttu-id="7a02a-156">Quita cualquier otra instantánea de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a02a-156">Drop any other database snapshots.</span></span>  
  
     <span data-ttu-id="7a02a-157">Para obtener información sobre cómo quitar instantáneas, vea [Eliminar una instantánea de base de datos &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7a02a-157">For information on dropping snapshots, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span> <span data-ttu-id="7a02a-158">Si la base de datos utiliza el modelo de recuperación completa, antes de revertir, se debe hacer una copia de seguridad del registro.</span><span class="sxs-lookup"><span data-stu-id="7a02a-158">If the database uses the full recovery model, before reverting, you should back up the log.</span></span> <span data-ttu-id="7a02a-159">Para obtener más información, vea [Realizar copia de seguridad de un registro de transacciones &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) o [Realizar una copia de seguridad del registro de transacciones cuando la base de datos está dañada &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7a02a-159">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) or [Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="7a02a-160">Realice la operación de reversión.</span><span class="sxs-lookup"><span data-stu-id="7a02a-160">Perform the revert operation.</span></span>  
  
     <span data-ttu-id="7a02a-161">Para realizar una operación de reversión es necesario disponer de permisos RESTORE DATABASE en la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="7a02a-161">A revert operation requires RESTORE DATABASE permissions on the source database.</span></span> <span data-ttu-id="7a02a-162">Para revertir la base de datos, use la siguiente instrucción Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="7a02a-162">To revert the database, use the following Transact-SQL statement:</span></span>  
  
     <span data-ttu-id="7a02a-163">RESTORE DATABASE *nombre_base_de_datos* FROM DATABASE_SNAPSHOT **=** _nombre_base_de_datos_de_instantánea_</span><span class="sxs-lookup"><span data-stu-id="7a02a-163">RESTORE DATABASE *database_name* FROM DATABASE_SNAPSHOT **=**_database_snapshot_name_</span></span>  
  
     <span data-ttu-id="7a02a-164">Donde *nombre_base_de_datos* es la base de datos de origen y *nombre_base_de_datos_de_instantánea* equivale al nombre de la instantánea a la que quiere revertir la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a02a-164">Where *database_name* is the source database and *database_snapshot_name* is the name of the snapshot to which you want to revert the database.</span></span> <span data-ttu-id="7a02a-165">Tenga en cuenta que en esta instrucción debe especificar un nombre de instantánea y no un dispositivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7a02a-165">Notice that in this statement, you must specify a snapshot name rather than a backup device.</span></span>  
  
     <span data-ttu-id="7a02a-166">Para obtener más información, vea [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a02a-166">For more information, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7a02a-167">Durante la operación de reversión, la instantánea y la base de datos de origen no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="7a02a-167">During the revert operation, both the snapshot and the source database are unavailable.</span></span> <span data-ttu-id="7a02a-168">La base de datos de origen y la instantánea están marcadas como "en restauración".</span><span class="sxs-lookup"><span data-stu-id="7a02a-168">The source database and snapshot are both marked as "In restore."</span></span> <span data-ttu-id="7a02a-169">Si se produce un error durante la operación de reversión, se intentará finalizar la reversión cuando se vuelva a iniciar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a02a-169">If an error occurs during the revert operation, it will try to finish reverting when the database starts up again.</span></span>  
  
4.  <span data-ttu-id="7a02a-170">Si el propietario de la base de datos ha cambiado desde la creación de la instantánea, se recomienda actualizar el propietario de la base de datos revertida.</span><span class="sxs-lookup"><span data-stu-id="7a02a-170">If the database owner changed since creation of the database snapshot, you may want to update the database owner of the reverted database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7a02a-171">La base de datos revertida conserva los permisos y la configuración (por ejemplo, el propietario de la base de datos y el modelo de recuperación) de la instantánea de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a02a-171">The reverted database retains the permissions and configuration (such as database owner and recovery model) of the database snapshot.</span></span>  
  
5.  <span data-ttu-id="7a02a-172">Inicie la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a02a-172">Start the database.</span></span>  
  
6.  <span data-ttu-id="7a02a-173">De manera opcional, realice una copia de seguridad de la base de datos revertida, especialmente si utiliza el modelo de recuperación completa (o por medio de registros de operaciones masivas).</span><span class="sxs-lookup"><span data-stu-id="7a02a-173">Optionally, back up the reverted database, especially if it uses the full (or bulk-logged) recovery model.</span></span> <span data-ttu-id="7a02a-174">Para realizar una copia de seguridad de una base de datos, vea [Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7a02a-174">To back up a database, see [Create a Full Database Backup &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="7a02a-175">Ejemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7a02a-175">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="7a02a-176">Esta sección contiene los siguientes ejemplos de reversión de una base de datos a una instantánea de base de datos:</span><span class="sxs-lookup"><span data-stu-id="7a02a-176">This section contains the following examples of reverting a database to a database snapshot:</span></span>  
  
-   <span data-ttu-id="7a02a-177">A.</span><span class="sxs-lookup"><span data-stu-id="7a02a-177">A.</span></span> [<span data-ttu-id="7a02a-178">Revertir una instantánea en la base de datos AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="7a02a-178">Reverting a snapshot on the AdventureWorks database</span></span>](#Reverting_AW)  
  
-   <span data-ttu-id="7a02a-179">B.</span><span class="sxs-lookup"><span data-stu-id="7a02a-179">B.</span></span> [<span data-ttu-id="7a02a-180">Revertir una instantánea en la base de datos Sales</span><span class="sxs-lookup"><span data-stu-id="7a02a-180">Reverting a snapshot on the Sales database</span></span>](#Reverting_Sales)  
  
####  <a name="a-reverting-a-snapshot-on-the-adventureworks-database"></a><a name="Reverting_AW"></a> <span data-ttu-id="7a02a-181">A.</span><span class="sxs-lookup"><span data-stu-id="7a02a-181">A.</span></span> <span data-ttu-id="7a02a-182">Revertir una instantánea en la base de datos AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="7a02a-182">Reverting a snapshot on the AdventureWorks database</span></span>  
 <span data-ttu-id="7a02a-183">En este ejemplo se considera que solo existe una instantánea en la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a02a-183">This example assumes that only one snapshot currently exists on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="7a02a-184">Para ver el ejemplo que crea la instantánea a la que se revierte la base de datos, vea [Crear una instantánea de base de datos &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7a02a-184">For the example that creates the snapshot to which the database is reverted here, see [Create a Database Snapshot &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span></span>  
  
```  
USE master;  
-- Reverting AdventureWorks to AdventureWorks_dbss1800  
RESTORE DATABASE AdventureWorks from   
DATABASE_SNAPSHOT = 'AdventureWorks_dbss1800';  
GO  
```  
  
####  <a name="b-reverting-a-snapshot-on-the-sales-database"></a><a name="Reverting_Sales"></a> <span data-ttu-id="7a02a-185">B.</span><span class="sxs-lookup"><span data-stu-id="7a02a-185">B.</span></span> <span data-ttu-id="7a02a-186">Revertir una instantánea en la base de datos Sales</span><span class="sxs-lookup"><span data-stu-id="7a02a-186">Reverting a snapshot on the Sales database</span></span>  
 <span data-ttu-id="7a02a-187">En este ejemplo se considera que hay dos instantáneas en la base de datos **Sales** : **sales_snapshot0600** y **sales_snapshot1200**.</span><span class="sxs-lookup"><span data-stu-id="7a02a-187">This example assumes that two snapshots currently exist on the **Sales** database: **sales_snapshot0600** and **sales_snapshot1200**.</span></span> <span data-ttu-id="7a02a-188">En el ejemplo, se elimina la instantánea más antigua y se revierte la base de datos a la instantánea más reciente.</span><span class="sxs-lookup"><span data-stu-id="7a02a-188">The example deletes the older of the snapshots and reverts the database to the more recent snapshot.</span></span>  
  
 <span data-ttu-id="7a02a-189">Para ver el código para crear la base de datos de ejemplo y las instantáneas de las que depende este ejemplo, vea:</span><span class="sxs-lookup"><span data-stu-id="7a02a-189">For the code for creating the sample database and snapshots on which this example depends, see:</span></span>  
  
-   <span data-ttu-id="7a02a-190">Para la base de datos **Sales** y la instantánea **sales_snapshot0600**, vea las secciones "Crear una base de datos con grupos de archivos" y "Crear una instantánea de base de datos" en [CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a02a-190">For the **Sales** database and the **sales_snapshot0600** snapshot, see "Creating a database with filegroups" and "Creating a database snapshot" in [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
-   <span data-ttu-id="7a02a-191">Para la base de datos **sales_snapshot1200** , vea "Crear una instantánea de la base datos Sales" en [Crear una instantánea de base de datos &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7a02a-191">For the **sales_snapshot1200** snapshot, see "Creating a snapshot on the Sales database" in [Create a Database Snapshot &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span></span>  
  
```  
--Test to see if sales_snapshot0600 exists and if it   
-- does, delete it.  
IF EXISTS (SELECT dbid FROM sys.databases  
    WHERE NAME='sales_snapshot0600')  
    DROP DATABASE SalesSnapshot0600;  
GO  
-- Reverting Sales to sales_snapshot1200  
USE master;  
RESTORE DATABASE Sales FROM DATABASE_SNAPSHOT = 'sales_snapshot1200';  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7a02a-192">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="7a02a-192">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7a02a-193">Crear una instantánea de base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7a02a-193">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="7a02a-194">Ver una instantánea de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7a02a-194">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="7a02a-195">Eliminar una instantánea de base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7a02a-195">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="7a02a-196">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a02a-196">See Also</span></span>  
 <span data-ttu-id="7a02a-197">[Instantáneas de bases de datos &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a02a-197">[Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span></span>  
 <span data-ttu-id="7a02a-198">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7a02a-198">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="7a02a-199">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7a02a-199">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="7a02a-200">Creación de reflejo e instantáneas de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7a02a-200">Database Mirroring and Database Snapshots &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-and-database-snapshots-sql-server.md)  
  
  
