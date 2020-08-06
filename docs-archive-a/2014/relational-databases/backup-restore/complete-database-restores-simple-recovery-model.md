---
title: Restauraciones de base de datos completas (modelo de recuperación simple) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- complete database restores
- database restores [SQL Server], complete database
- restoring databases [SQL Server], complete database
- simple recovery model [SQL Server]
- restoring [SQL Server], database
ms.assetid: 49828927-1727-4d1d-9ef5-3de43f68c026
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67eee8d7d6f44c9ff83795bf2a8bd612309bf0a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677716"
---
# <a name="complete-database-restores-simple-recovery-model"></a><span data-ttu-id="62e15-102">Restauraciones de base de datos completas (modelo de recuperación simple)</span><span class="sxs-lookup"><span data-stu-id="62e15-102">Complete Database Restores (Simple Recovery Model)</span></span>
  <span data-ttu-id="62e15-103">El objetivo de una restauración completa de la base de datos es restaurar toda la base de datos.</span><span class="sxs-lookup"><span data-stu-id="62e15-103">In a complete database restore, the goal is to restore the whole database.</span></span> <span data-ttu-id="62e15-104">Durante el proceso de restauración, la base de datos completa se encuentra sin conexión.</span><span class="sxs-lookup"><span data-stu-id="62e15-104">The whole database is offline for the duration of the restore.</span></span> <span data-ttu-id="62e15-105">Antes de que ninguna parte de la base de datos esté en línea, se recuperan todos los datos a un punto coherente en el que todas las partes de la base de datos se encuentran en el mismo momento y en el que no existe ninguna transacción sin confirmar.</span><span class="sxs-lookup"><span data-stu-id="62e15-105">Before any part of the database can come online, all data is recovered to a consistent point in which all parts of the database are at the same point in time and no uncommitted transactions exist.</span></span>  
  
 <span data-ttu-id="62e15-106">En el modelo de recuperación simple, no se puede restaurar la base de datos a un momento concreto de una copia de seguridad específica.</span><span class="sxs-lookup"><span data-stu-id="62e15-106">Under the simple recovery model, the database cannot be restored to a specific point in time within a specific backup.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="62e15-107">Se recomienda no adjuntar ni restaurar bases de datos de orígenes desconocidos o que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="62e15-107">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="62e15-108">Estas bases de datos pueden contener código malintencionado que podría ejecutar código [!INCLUDE[tsql](../../../includes/tsql-md.md)] inesperado o provocar errores debido a la modificación del esquema o de la estructura de la base de datos física.</span><span class="sxs-lookup"><span data-stu-id="62e15-108">These databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="62e15-109">Para usar una base de datos desde un origen desconocido o que no sea de confianza, ejecute [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) en la base de datos de un servidor que no sea de producción y examine también el código, como procedimientos almacenados u otro código definido por el usuario, en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="62e15-109">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  

  
> [!NOTE]  
>  <span data-ttu-id="62e15-110">Para obtener más información sobre la compatibilidad con las copias de seguridad de versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea la sección "Soporte de compatibilidad" de [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62e15-110">For information about support for backups from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the "Compatibility Support" section of [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="overview-of-database-restore-under-the-simple-recovery-model"></a><a name="Overview"></a> <span data-ttu-id="62e15-111">Información general de la restauración de la base de datos en el modelo de recuperación simple</span><span class="sxs-lookup"><span data-stu-id="62e15-111">Overview of Database Restore Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="62e15-112">Una restauración completa de base de datos con el modelo de recuperación simple implica una o dos instrucciones [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , en función de si desea restaurar una copia de seguridad diferencial de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="62e15-112">A full database restore under the simple recovery model involves one or two [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statements, depending on whether you want to restore a differential database backup.</span></span> <span data-ttu-id="62e15-113">Si solo usa copias de seguridad completas de la base de datos, restaure solo la copia de seguridad más reciente, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="62e15-113">If you are using only a full database backup, just restore the most recent backup, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="62e15-114">![Restauración exclusiva de una copia de seguridad completa de la base de datos](../../database-engine/media/bnrr-rmsimple1-fulldbbu.gif "Restauración exclusiva de una copia de seguridad completa de la base de datos")</span><span class="sxs-lookup"><span data-stu-id="62e15-114">![Restoring only a full database backup](../../database-engine/media/bnrr-rmsimple1-fulldbbu.gif "Restoring only a full database backup")</span></span>  
  
 <span data-ttu-id="62e15-115">Si también usa una copia de seguridad diferencial de la base de datos, restaure la copia de seguridad completa más reciente de la base de datos sin recuperar la base de datos y, a continuación, restaure la copia de seguridad diferencial más reciente de la base de datos y recupere la base de datos.</span><span class="sxs-lookup"><span data-stu-id="62e15-115">If you are also using a differential database backup, restore the most recent full database backup without recovering the database, and then restore the most recent differential database backup and recover the database.</span></span> <span data-ttu-id="62e15-116">En la siguiente ilustración se muestra este proceso.</span><span class="sxs-lookup"><span data-stu-id="62e15-116">The following illustration shows this process.</span></span>  
  
 <span data-ttu-id="62e15-117">![Restaurar copias de seguridad de bases de datos completas y diferenciales](../../database-engine/media/bnrr-rmsimple2-diffdbbu.gif "Restaurar copias de seguridad de bases de datos completas y diferenciales")</span><span class="sxs-lookup"><span data-stu-id="62e15-117">![Restoring full and differential database backups](../../database-engine/media/bnrr-rmsimple2-diffdbbu.gif "Restoring full and differential database backups")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62e15-118">Si planea restaurar una copia de seguridad de la base de datos en una instancia de servidor distinta, vea [Copiar bases de datos con Copias de seguridad y restauración](../databases/copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="62e15-118">If you plan to restore a database backup onto a different server instance, see [Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md).</span></span>  
  
###  <a name="basic-transact-sql-restore-syntax"></a><a name="TsqlSyntax"></a> <span data-ttu-id="62e15-119">Sintaxis RESTORE de Transact-SQL básica</span><span class="sxs-lookup"><span data-stu-id="62e15-119">Basic Transact-SQL RESTORE Syntax</span></span>  
 <span data-ttu-id="62e15-120">La sintaxis [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) básica para restaurar una copia de seguridad de base de datos completa es:</span><span class="sxs-lookup"><span data-stu-id="62e15-120">The basic [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for restoring a full database backup is:</span></span>  
  
 <span data-ttu-id="62e15-121">RESTORE DATABASE *database_name* FROM *backup_device* [ WITH NORECOVERY ]</span><span class="sxs-lookup"><span data-stu-id="62e15-121">RESTORE DATABASE *database_name* FROM *backup_device* [ WITH NORECOVERY ]</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62e15-122">Use WITH NORECOVERY si también desea restaurar una copia de seguridad diferencial de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="62e15-122">Use WITH NORECOVERY if you plan to also restore a differential database backup.</span></span>  
  
 <span data-ttu-id="62e15-123">La sintaxis [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) básica para restaurar una copia de seguridad de la base de datos es:</span><span class="sxs-lookup"><span data-stu-id="62e15-123">The basic [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for restoring a database backup is:</span></span>  
  
 <span data-ttu-id="62e15-124">RESTORE DATABASE *database_name* FROM *backup_device* WITH RECOVERY</span><span class="sxs-lookup"><span data-stu-id="62e15-124">RESTORE DATABASE *database_name* FROM *backup_device* WITH RECOVERY</span></span>  
  
###  <a name="example-transact-sql"></a><a name="Example"></a> <span data-ttu-id="62e15-125">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="62e15-125">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="62e15-126">En el siguiente ejemplo se muestra primero cómo usar la instrucción [BACKUP](/sql/t-sql/statements/backup-transact-sql) para crear una copia de seguridad completa y diferencial de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62e15-126">The following example first shows how to use the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement to create a full database backup and a differential database backup of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="62e15-127">A continuación, se restauran estas copias de seguridad una después de la otra.</span><span class="sxs-lookup"><span data-stu-id="62e15-127">The example then restores these backups in sequence.</span></span> <span data-ttu-id="62e15-128">La base de datos se restaura a su estado en el momento en que finalizó la copia de seguridad diferencial.</span><span class="sxs-lookup"><span data-stu-id="62e15-128">The database is restored to its state as of the time that the differential database backup finished.</span></span>  
  
 <span data-ttu-id="62e15-129">En el ejemplo se muestran las opciones críticas de una secuencia de restauración en un escenario de restauración de base de datos completa.</span><span class="sxs-lookup"><span data-stu-id="62e15-129">The example shows the critical options in a restore sequence for the complete database restore scenario.</span></span> <span data-ttu-id="62e15-130">Una *secuencia de restauración* consta de dos o más operaciones de restauración que mueven datos en una o varias fases de restauración.</span><span class="sxs-lookup"><span data-stu-id="62e15-130">A *restore sequence* consists of one or more restore operations that move data through one or more of the phases of restore.</span></span> <span data-ttu-id="62e15-131">La sintaxis y los detalles no pertinentes para este propósito se omiten.</span><span class="sxs-lookup"><span data-stu-id="62e15-131">Syntax and details that are not relevant to this purpose are omitted.</span></span> <span data-ttu-id="62e15-132">Al recuperar una base de datos, se recomienda especificar explícitamente la opción RECOVERY por motivos de claridad, aunque es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="62e15-132">When you recover a database, we recommend explicitly specifying the RECOVERY option for clarity, even though it is the default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62e15-133">En el ejemplo se comienza con una instrucción [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) que establece el modelo de recuperación en `SIMPLE`.</span><span class="sxs-lookup"><span data-stu-id="62e15-133">The example starts with an [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement that sets the recovery model to `SIMPLE`.</span></span>  
  
```  
USE master;  
--Make sure the database is using the simple recovery model.  
ALTER DATABASE AdventureWorks2012 SET RECOVERY SIMPLE;  
GO  
-- Back up the full AdventureWorks2012 database.  
BACKUP DATABASE AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
  WITH FORMAT;  
GO  
--Create a differential database backup.  
BACKUP DATABASE AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'  
   WITH DIFFERENTIAL;  
GO  
--Restore the full database backup (from backup set 1).  
RESTORE DATABASE AdventureWorks2012   
FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
   WITH FILE=1, NORECOVERY;  
--Restore the differential backup (from backup set 2).  
RESTORE DATABASE AdventureWorks2012   
FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
   WITH FILE=2, RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="62e15-134">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="62e15-134">Related Tasks</span></span>  
 <span data-ttu-id="62e15-135">**Para restaurar una copia de seguridad completa de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="62e15-135">**To restore a full database backup**</span></span>  
  
-   [<span data-ttu-id="62e15-136">Restaurar una copia de seguridad de base de datos en el modelo de recuperación simple &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="62e15-136">Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md)  
  
-   [<span data-ttu-id="62e15-137">Restaurar una copia de seguridad de base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="62e15-137">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="62e15-138">Restaurar una base de datos a una nueva ubicación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="62e15-138">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
 <span data-ttu-id="62e15-139">**Para restaurar una copia de seguridad diferencial de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="62e15-139">**To restore a differential database backup**</span></span>  
  
-   [<span data-ttu-id="62e15-140">Restaurar una copia de seguridad diferencial de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="62e15-140">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](restore-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="62e15-141">**Para restaurar una copia de seguridad mediante los objetos de administración de SQL Server (SMO)**</span><span class="sxs-lookup"><span data-stu-id="62e15-141">**To restore a backup by using SQL Server Management Objects (SMO)**</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  

  
## <a name="see-also"></a><span data-ttu-id="62e15-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62e15-142">See Also</span></span>  
 <span data-ttu-id="62e15-143">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="62e15-143">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="62e15-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="62e15-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="62e15-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="62e15-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="62e15-146">[Copias de seguridad completas de bases de datos &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="62e15-146">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="62e15-147">[Copias de seguridad diferenciales &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="62e15-147">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="62e15-148">[Información general de copia de seguridad &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="62e15-148">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="62e15-149">Información general sobre restauración y recuperación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="62e15-149">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
  
  
