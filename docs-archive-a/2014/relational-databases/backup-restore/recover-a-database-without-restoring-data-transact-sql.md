---
title: Recuperación de una base de datos sin restaurar los datos (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring [SQL Server], recovery-only
- recovery-only scenario [SQL Server]
- restoring databases [SQL Server], recovery-only
- recovery [SQL Server], recovery-only
- database recovery [SQL Server]
- database restores [SQL Server], recovery-only
- recovery [SQL Server], without restoring data
ms.assetid: 7e8fa620-315d-4e10-a718-23fa5171c09e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 04e4f78e51adb803bb65530c0b3b903aa7f76419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675471"
---
# <a name="recover-a-database-without-restoring-data-transact-sql"></a><span data-ttu-id="ce965-102">Recuperar una base de datos sin restaurar los datos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ce965-102">Recover a Database Without Restoring Data (Transact-SQL)</span></span>
  <span data-ttu-id="ce965-103">Normalmente, todos los datos de una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se restauran antes de que se recupere la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ce965-103">Usually, all of the data in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is restored before the database is recovered.</span></span> <span data-ttu-id="ce965-104">Sin embargo, una operación de restauración puede recuperar una base de datos sin restaurar realmente una copia de seguridad; por ejemplo, al recuperar un archivo de solo lectura que es coherente con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ce965-104">However, a restore operation can recover a database without actually restoring a backup; for example, when recovering a read-only file that is consistent with the database.</span></span> <span data-ttu-id="ce965-105">Esto se conoce como *restauración de solo recuperación*.</span><span class="sxs-lookup"><span data-stu-id="ce965-105">This is referred to as a *recovery-only restore*.</span></span> <span data-ttu-id="ce965-106">Cuando los datos sin conexión ya son coherentes con la base de datos y solo es necesario lograr que estén disponibles, una operación de solo restauración completa la recuperación de la base de datos y pone los datos en línea.</span><span class="sxs-lookup"><span data-stu-id="ce965-106">When offline data is already consistent with the database and needs only to be made available, a recovery-only restore operation completes the recovery of the database and bring the data online.</span></span>  
  
 <span data-ttu-id="ce965-107">Una restauración de solo recuperación se puede realizar para una base de datos completa o para uno o varios archivos o grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="ce965-107">A recovery-only restore can occur for a whole database or for one or more a files or filegroups.</span></span>  
  
## <a name="recovery-only-database-restore"></a><span data-ttu-id="ce965-108">Restauración de solo recuperación de la base de datos</span><span class="sxs-lookup"><span data-stu-id="ce965-108">Recovery-Only Database Restore</span></span>  
 <span data-ttu-id="ce965-109">Una restauración de solo recuperación de base de datos puede resultar útil en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="ce965-109">A recovery-only database restore can be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="ce965-110">No se recuperó la base de datos al restaurar la última copia de seguridad en una secuencia de restauración y ahora se desea recuperar la base de datos para ponerla en línea.</span><span class="sxs-lookup"><span data-stu-id="ce965-110">You did not recover the database when restoring the last backup in a restore sequence, and you now want to recover the database to bring it online.</span></span>  
  
-   <span data-ttu-id="ce965-111">La base de datos está en modo de espera y desea que se pueda actualizarla sin aplicar otra copia de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="ce965-111">The database is in standby mode, and you want to make the database updatable without applying another log backup.</span></span>  
  
 <span data-ttu-id="ce965-112">La sintaxis de [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) para una restauración de solo recuperación de bases de datos es:</span><span class="sxs-lookup"><span data-stu-id="ce965-112">The [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for a recovery-only database restore is as follows:</span></span>  
  
 <span data-ttu-id="ce965-113">RESTORE DATABASE *database_name* WITH RECOVERY</span><span class="sxs-lookup"><span data-stu-id="ce965-113">RESTORE DATABASE *database_name* WITH RECOVERY</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce965-114">La cláusula FROM **=** \<*backup_device>\* no se usa en las restauraciones de solo recuperación porque no es necesario hacer una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ce965-114">The FROM **=** \<*backup_device>\* clause is not used for recovery-only restores because no backup is necessary.</span></span>  
  
 <span data-ttu-id="ce965-115">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="ce965-115">**Example**</span></span>  
  
 <span data-ttu-id="ce965-116">En el siguiente ejemplo se recupera la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] en una operación de restauración sin restaurar los datos.</span><span class="sxs-lookup"><span data-stu-id="ce965-116">The following example recovers the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database in a restore operation without restoring data.</span></span>  
  
```  
-- Restore database using WITH RECOVERY.  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY  
```  
  
## <a name="recovery-only-file-restore"></a><span data-ttu-id="ce965-117">Restauración de solo recuperación</span><span class="sxs-lookup"><span data-stu-id="ce965-117">Recovery-Only File Restore</span></span>  
 <span data-ttu-id="ce965-118">Una restauración de solo recuperación puede resultar útil en la siguiente situación:</span><span class="sxs-lookup"><span data-stu-id="ce965-118">A recovery-only file restore can be useful in the following situation:</span></span>  
  
 <span data-ttu-id="ce965-119">Una base de datos se restaura por etapas.</span><span class="sxs-lookup"><span data-stu-id="ce965-119">A database is restored piecemeal.</span></span> <span data-ttu-id="ce965-120">Una vez finalizada la restauración del grupo de archivos principal, uno o varios de los archivos no restaurados son coherentes con el nuevo estado de la base de datos; esto puede deberse a que la base de datos ha sido de solo lectura durante algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="ce965-120">After restore of the primary filegroup is complete, one or more of the unrestored files are consistent with the new database state, perhaps because it has been read-only for some time.</span></span> <span data-ttu-id="ce965-121">Estos archivos solo necesitan recuperarse, no es necesario copiar los datos.</span><span class="sxs-lookup"><span data-stu-id="ce965-121">These files only have to be recovered; data copying is unnecessary.</span></span>  
  
 <span data-ttu-id="ce965-122">En una operación de restauración de solo recuperación los datos del grupo de archivos sin conexión pasan a estar en línea; no se produce ninguna fase de copia de datos, puesta al día ni reversión.</span><span class="sxs-lookup"><span data-stu-id="ce965-122">A recovery-only restore operation brings the data in the offline filegroup online; no data-copy, redo, or undo phase occurs.</span></span> <span data-ttu-id="ce965-123">Para obtener más información sobre las fases de restauración, vea [Información general sobre restauración y recuperación &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ce965-123">For information about the phases of restore, see [Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span></span>  
  
 <span data-ttu-id="ce965-124">La sintaxis de [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) para una restauración de solo recuperación de archivos es:</span><span class="sxs-lookup"><span data-stu-id="ce965-124">The [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for a recovery-only file restore is:</span></span>  
  
 <span data-ttu-id="ce965-125">RESTOre DATABASE *database_name* {file **=** _logical_file_name_ | **=** _Logical_filegroup_name_ **de grupo de**archivos} [,... *n* ] con recuperación</span><span class="sxs-lookup"><span data-stu-id="ce965-125">RESTORE DATABASE *database_name* { FILE **=**_logical_file_name_ | FILEGROUP **=**_logical_filegroup_name_ }[ **,**...*n* ] WITH RECOVERY</span></span>  
  
 <span data-ttu-id="ce965-126">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="ce965-126">**Example**</span></span>  
  
 <span data-ttu-id="ce965-127">En el siguiente ejemplo, se muestra una restauración de solo recuperación de archivos de los archivos de un grupo de archivos secundario, `SalesGroup2`, de la base de datos `Sales` .</span><span class="sxs-lookup"><span data-stu-id="ce965-127">The following example illustrates a recovery-only file restore of the files in a secondary filegroup, `SalesGroup2`, in the `Sales` database.</span></span> <span data-ttu-id="ce965-128">El grupo de archivos principal ya se ha restaurado como paso inicial de una restauración por etapas y `SalesGroup2` es coherente con el grupo de archivos principal restaurado.</span><span class="sxs-lookup"><span data-stu-id="ce965-128">The primary filegroup has already been restored as the initial step of a piecemeal restore, and `SalesGroup2` is consistent with the restored primary filegroup.</span></span> <span data-ttu-id="ce965-129">Recuperar este grupo de archivos y ponerlo en línea requiere una única instrucción.</span><span class="sxs-lookup"><span data-stu-id="ce965-129">Recovering this filegroup and bringing it online requires only a single statement.</span></span>  
  
```  
RESTORE DATABASE Sales FILEGROUP=SalesGroup2 WITH RECOVERY;  
```  
  
## <a name="examples-of-completing-a-piecemeal-restore-scenario-with-a-recovery-only-restore"></a><span data-ttu-id="ce965-130">Ejemplos de llevar a cabo una restauración por etapas con una restauración de solo recuperación</span><span class="sxs-lookup"><span data-stu-id="ce965-130">Examples of Completing a Piecemeal Restore Scenario with a Recovery-Only Restore</span></span>  
 <span data-ttu-id="ce965-131">**Modelo de recuperación simple**</span><span class="sxs-lookup"><span data-stu-id="ce965-131">**Simple recovery model**</span></span>  
  
-   [<span data-ttu-id="ce965-132">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="ce965-132">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="ce965-133">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="ce965-133">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
 <span data-ttu-id="ce965-134">**Modelo de recuperación completa**</span><span class="sxs-lookup"><span data-stu-id="ce965-134">**Full recovery model**</span></span>  
  
-   [<span data-ttu-id="ce965-135">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="ce965-135">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="ce965-136">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="ce965-136">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  
## <a name="see-also"></a><span data-ttu-id="ce965-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce965-137">See Also</span></span>  
 <span data-ttu-id="ce965-138">[Restauración con conexión &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ce965-138">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="ce965-139">[Restauraciones por etapas &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ce965-139">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="ce965-140">[Restauraciones de archivos &#40;modelo de recuperación simple&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="ce965-140">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="ce965-141">[Restauraciones de archivos &#40;modelo de recuperación completa&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="ce965-141">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="ce965-142">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ce965-142">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
