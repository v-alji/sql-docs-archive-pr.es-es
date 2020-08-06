---
title: 'Ejemplo: restauración por etapas de la base de datos (modelo de recuperación completa) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- piecemeal restores [SQL Server], full recovery model
- restore sequences [SQL Server], piecemeal
ms.assetid: 0a84892d-2f7a-4e77-b2d0-d68b95595210
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5cfccccdbdc0c4fb3b189ee0a9fa3aeaf426578b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747645"
---
# <a name="example-piecemeal-restore-of-database-full-recovery-model"></a><span data-ttu-id="6059b-102">Ejemplo: Restauración por etapas de la base de datos (modelo de recuperación completa)</span><span class="sxs-lookup"><span data-stu-id="6059b-102">Example: Piecemeal Restore of Database (Full Recovery Model)</span></span>
  <span data-ttu-id="6059b-103">En una secuencia de restauración por etapas se restaura y recupera una base de datos en fases en el nivel del grupo de archivos, empezando con los grupos de archivos principales, los de lectura y escritura, y los secundarios.</span><span class="sxs-lookup"><span data-stu-id="6059b-103">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, beginning with the primary and all read-write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="6059b-104">En este ejemplo, la base de datos `adb` se restaura en un nuevo equipo después de un desastre.</span><span class="sxs-lookup"><span data-stu-id="6059b-104">In this example, database `adb` is restored to a new computer after a disaster.</span></span> <span data-ttu-id="6059b-105">La base de datos está utilizando el modelo de recuperación completa, por lo que, antes de iniciar la restauración, debe crearse una copia del final del registro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6059b-105">The database is using the full recovery model; therefore, before the restore starts, a tail-log backup must be taken of the database.</span></span> <span data-ttu-id="6059b-106">Antes del desastre, todos los grupos de archivos están en línea.</span><span class="sxs-lookup"><span data-stu-id="6059b-106">Before the disaster, all the filegroups are online.</span></span> <span data-ttu-id="6059b-107">El grupo de archivos `B` es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="6059b-107">Filegroup `B` is read-only.</span></span> <span data-ttu-id="6059b-108">Se deben restaurar todos los grupos de archivos secundarios, pero por orden de importancia: `A` (el de mayor importancia), `C`y, por último, `B`.</span><span class="sxs-lookup"><span data-stu-id="6059b-108">All of the secondary filegroups must be restored, but they are restored in order of importance: `A` (highest), `C`, and lastly `B`.</span></span> <span data-ttu-id="6059b-109">En este ejemplo, hay cuatro copias de seguridad de registros, incluida la copia del final del registro.</span><span class="sxs-lookup"><span data-stu-id="6059b-109">In this example, there are four log backups, including the tail-log backup.</span></span>  
  
## <a name="tail-log-backup"></a><span data-ttu-id="6059b-110">Copia del final del registro</span><span class="sxs-lookup"><span data-stu-id="6059b-110">Tail-Log Backup</span></span>  
 <span data-ttu-id="6059b-111">Antes de restaurar la base de datos, el administrador de la base de datos debe realizar una copia de seguridad de registros después del error.</span><span class="sxs-lookup"><span data-stu-id="6059b-111">Before restoring the database, the database administrator must back up the tail of the log.</span></span> <span data-ttu-id="6059b-112">Puesto que la base de datos está dañada, es necesario usar la opción NO_TRUNCATE al realizar la copia del final del registro:</span><span class="sxs-lookup"><span data-stu-id="6059b-112">Because the database is damaged, creating the tail-log backup requires using the NO_TRUNCATE option:</span></span>  
  
```  
BACKUP LOG adb TO tailLogBackup WITH NORECOVERY, NO_TRUNCATE  
```  
  
 <span data-ttu-id="6059b-113">La copia del final del registro es la última copia de seguridad que se aplica en las secuencias de restauración siguientes.</span><span class="sxs-lookup"><span data-stu-id="6059b-113">The tail-log backup is the last backup that is applied in the following restore sequences.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="6059b-114">Secuencias de restauración</span><span class="sxs-lookup"><span data-stu-id="6059b-114">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6059b-115">La sintaxis de un flujo de restauración en línea es la misma que la de un flujo de restauración sin conexión.</span><span class="sxs-lookup"><span data-stu-id="6059b-115">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="6059b-116">Restauración parcial del grupo de archivos principal y secundario `A`.</span><span class="sxs-lookup"><span data-stu-id="6059b-116">Partial restore of the primary and secondary filegroup `A`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='Primary' FROM backup1   
       WITH PARTIAL, NORECOVERY  
    RESTORE DATABASE adb FILEGROUP='A' FROM backup2   
       WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM backup4 WITH NORECOVERY  
    RESTORE LOG adb FROM backup5 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
2.  <span data-ttu-id="6059b-117">Restauración con conexión del grupo de archivos `C`.</span><span class="sxs-lookup"><span data-stu-id="6059b-117">Online restore of filegroup `C`.</span></span>  
  
     <span data-ttu-id="6059b-118">En este momento, el grupo de archivos principal y el secundario `A` están en línea.</span><span class="sxs-lookup"><span data-stu-id="6059b-118">At this point, the primary filegroup and secondary filegroup `A` are online.</span></span> <span data-ttu-id="6059b-119">Todos los archivos de los grupos de archivos `B` y `C` están pendientes de recuperación y sin conexión.</span><span class="sxs-lookup"><span data-stu-id="6059b-119">All the files in filegroups `B` and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
     <span data-ttu-id="6059b-120">Los mensajes de la última instrucción `RESTORE LOG` del paso 1 indican que la reversión de las transacciones en las que interviene el grupo de archivos `C` se ha diferido porque este grupo de archivos no está disponible.</span><span class="sxs-lookup"><span data-stu-id="6059b-120">Messages from the last `RESTORE LOG` statement in step 1 indicate that rollback of transactions that involve filegroup `C` was deferred, because this filegroup is not available.</span></span> <span data-ttu-id="6059b-121">Las operaciones periódicas pueden continuar, pero estas transacciones mantienen los bloqueos y no se truncará el registro hasta que se pueda completar la reversión.</span><span class="sxs-lookup"><span data-stu-id="6059b-121">Regular operations can continue, but locks are held by these transactions and log truncation will not occur until the rollback can complete.</span></span>  
  
     <span data-ttu-id="6059b-122">En la segunda secuencia de restauración, el administrador de la base de datos restaura el grupo de archivos `C`:</span><span class="sxs-lookup"><span data-stu-id="6059b-122">In the second restore sequence, the database administrator restores filegroup `C`:</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='C' FROM backup2a WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM backup4 WITH NORECOVERY  
    RESTORE LOG adb FROM backup5 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="6059b-123">En este momento, los grupos de archivos principal, `A` y `C` están en línea.</span><span class="sxs-lookup"><span data-stu-id="6059b-123">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="6059b-124">Los archivos del grupo `B` permanecen pendientes de recuperación, con el grupo de archivos sin conexión.</span><span class="sxs-lookup"><span data-stu-id="6059b-124">Files in filegroup `B` remain recovery pending, with the filegroup offline.</span></span> <span data-ttu-id="6059b-125">Las transacciones diferidas se han resuelto y se trunca el registro.</span><span class="sxs-lookup"><span data-stu-id="6059b-125">Deferred transactions have been resolved, and log truncation occurs.</span></span>  
  
3.  <span data-ttu-id="6059b-126">Restauración con conexión del grupo de archivos `B`.</span><span class="sxs-lookup"><span data-stu-id="6059b-126">Online restore of filegroup `B`.</span></span>  
  
     <span data-ttu-id="6059b-127">En la tercera secuencia de restauración, el administrador de la base de datos restaura el grupo de archivos `B`.</span><span class="sxs-lookup"><span data-stu-id="6059b-127">In the third restore sequence, the database administrator restores filegroup `B`.</span></span> <span data-ttu-id="6059b-128">La copia de seguridad del grupo de archivos `B` se realizó después de cambiar el grupo a solo lectura, por lo que no es necesario ponerlo al día durante la recuperación.</span><span class="sxs-lookup"><span data-stu-id="6059b-128">The backup of filegroup `B` was taken after the filegroup became read-only; therefore, it does not have to be rolled forward during recovery.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup2b WITH RECOVERY  
    ```  
  
     <span data-ttu-id="6059b-129">Todos los grupos de archivos están ahora en línea.</span><span class="sxs-lookup"><span data-stu-id="6059b-129">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="6059b-130">Otros ejemplos</span><span class="sxs-lookup"><span data-stu-id="6059b-130">Additional Examples</span></span>  
  
-   [<span data-ttu-id="6059b-131">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="6059b-131">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="6059b-132">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="6059b-132">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="6059b-133">Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="6059b-133">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="6059b-134">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="6059b-134">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="6059b-135">Ejemplo: restauración con conexión de un archivo de lectura/escritura &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="6059b-135">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="6059b-136">Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="6059b-136">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="6059b-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6059b-137">See Also</span></span>  
 <span data-ttu-id="6059b-138">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6059b-138">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="6059b-139">[Restauración con conexión &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6059b-139">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="6059b-140">[Aplicar copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6059b-140">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="6059b-141">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6059b-141">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="6059b-142">Restauraciones por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6059b-142">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
