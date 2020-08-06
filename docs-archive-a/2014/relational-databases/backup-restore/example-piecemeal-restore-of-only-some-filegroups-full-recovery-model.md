---
title: 'Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos (modelo de recuperación completa) | Microsoft Docs'
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
ms.assetid: bced4b54-e819-472b-b784-c72e14e72a0b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b3cb1a5ea33a5016c99fdf1f5a7f4e892c045b59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751217"
---
# <a name="example-piecemeal-restore-of-only-some-filegroups-full-recovery-model"></a><span data-ttu-id="6a84c-102">Ejemplo: Restauración por etapas exclusiva para algunos grupos de archivos (modelo de recuperación completa)</span><span class="sxs-lookup"><span data-stu-id="6a84c-102">Example: Piecemeal Restore of Only Some Filegroups (Full Recovery Model)</span></span>
  <span data-ttu-id="6a84c-103">Este tema solo es de interés para las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contengan varios archivos o grupos de archivos con el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="6a84c-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="6a84c-104">En una secuencia de restauración por etapas restaura y recupera una base de datos en fases en el nivel del grupo de archivos, empezando con los grupos de archivos principales y todos los secundarios de lectura/escritura.</span><span class="sxs-lookup"><span data-stu-id="6a84c-104">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, starting with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="6a84c-105">En este ejemplo, una base de datos llamada `adb`, que utiliza el modelo de recuperación completa, contiene tres grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="6a84c-105">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="6a84c-106">El grupo de archivos `A` es de lectura/escritura, mientras que los grupos de archivos `B` y `C` son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="6a84c-106">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="6a84c-107">Inicialmente, todos los grupos de archivos están en línea.</span><span class="sxs-lookup"><span data-stu-id="6a84c-107">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="6a84c-108">Parece que el grupo de archivos principal y el `B` de la base de datos `adb` están dañados.</span><span class="sxs-lookup"><span data-stu-id="6a84c-108">The primary and filegroup `B` of database `adb` appear to be damaged.</span></span> <span data-ttu-id="6a84c-109">El grupo de archivos principal es bastante más que pequeño y puede restaurarse con rapidez.</span><span class="sxs-lookup"><span data-stu-id="6a84c-109">The primary filegroup is fairly small and can be restored quickly.</span></span> <span data-ttu-id="6a84c-110">El administrador de la base de datos decide restaurarlos utilizando una secuencia de restauración por etapas.</span><span class="sxs-lookup"><span data-stu-id="6a84c-110">The database administrator decides to restore them by using a piecemeal restore sequence.</span></span> <span data-ttu-id="6a84c-111">En primer lugar se restauran el grupo de archivos principal y los registros de transacciones posteriores y luego se recupera la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6a84c-111">First, the primary filegroup and the subsequent transaction logs are restored the database is recovered.</span></span>  
  
 <span data-ttu-id="6a84c-112">Los grupos de archivos intactos `A` y `C` incluyen información fundamental.</span><span class="sxs-lookup"><span data-stu-id="6a84c-112">The intact filegroups `A` and `C` contain critical data.</span></span> <span data-ttu-id="6a84c-113">Por lo tanto, se recuperarán a continuación para ponerlos en línea tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="6a84c-113">Therefore, they will be recovered next to bring them online as quickly as possible.</span></span> <span data-ttu-id="6a84c-114">Por último, se restaurará y recuperará el grupo de archivos secundario dañado, el `B`.</span><span class="sxs-lookup"><span data-stu-id="6a84c-114">Finally, the damaged secondary filegroup, `B`, is restored and recovered.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="6a84c-115">Secuencias de restauración:</span><span class="sxs-lookup"><span data-stu-id="6a84c-115">Restore Sequences:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6a84c-116">La sintaxis de un flujo de restauración en línea es la misma que la de un flujo de restauración sin conexión.</span><span class="sxs-lookup"><span data-stu-id="6a84c-116">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="6a84c-117">Cree una copia del final del registro de la base de datos `adb`.</span><span class="sxs-lookup"><span data-stu-id="6a84c-117">Create a tail log backup of database `adb`.</span></span> <span data-ttu-id="6a84c-118">Este paso es esencial para actualizar los grupos de archivos `A` y `C` intactos respecto al punto de recuperación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6a84c-118">This step is essential to make the intact filegroups `A` and `C` current with the recovery point of the database.</span></span>  
  
    ```  
    BACKUP LOG adb TO tailLogBackup WITH NORECOVERY  
    ```  
  
2.  <span data-ttu-id="6a84c-119">Restauración parcial del grupo de archivos principal.</span><span class="sxs-lookup"><span data-stu-id="6a84c-119">Partial restore of the primary filegroup.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='Primary' FROM backup   
    WITH PARTIAL, NORECOVERY  
    RESTORE LOG adb FROM backup1 WITH NORECOVERY  
    RESTORE LOG adb FROM backup2 WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="6a84c-120">En este momento, el grupo principal está en línea.</span><span class="sxs-lookup"><span data-stu-id="6a84c-120">At this point the primary is online.</span></span> <span data-ttu-id="6a84c-121">La recuperación de los archivos de los grupos `A`, `B`y `C` está pendiente, por lo que estos grupos de archivo están sin conexión.</span><span class="sxs-lookup"><span data-stu-id="6a84c-121">Files in filegroups `A`, `B`, and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
3.  <span data-ttu-id="6a84c-122">Restauración en línea de los grupos de archivos `A` y `C`.</span><span class="sxs-lookup"><span data-stu-id="6a84c-122">Online restore of filegroups `A` and `C`.</span></span>  
  
     <span data-ttu-id="6a84c-123">Dado que estos datos no están dañados, no es preciso restaurar los grupos de archivos a partir de la copia de seguridad. Sin embargo, es necesario recuperarlos para volver a ponerlos en línea.</span><span class="sxs-lookup"><span data-stu-id="6a84c-123">Because their data is undamaged, these filegroups do not have to be restored from a backup, but they do have to be recovered to bring them online.</span></span>  
  
     <span data-ttu-id="6a84c-124">El administrador de la base de datos recupera `A` y `C` inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="6a84c-124">The database administrator recovers `A` and `C` immediately.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='A', FILEGROUP='C' WITH RECOVERY  
    ```  
  
     <span data-ttu-id="6a84c-125">En este momento, los grupos de archivos principal, `A` y `C` están en línea.</span><span class="sxs-lookup"><span data-stu-id="6a84c-125">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="6a84c-126">Los archivos del grupo `B` permanecen pendientes de recuperación, con el grupo de archivos sin conexión.</span><span class="sxs-lookup"><span data-stu-id="6a84c-126">Files in filegroup `B` remain recovery pending, with the filegroup offline.</span></span>  
  
4.  <span data-ttu-id="6a84c-127">Restauración con conexión del grupo de archivos `B`.</span><span class="sxs-lookup"><span data-stu-id="6a84c-127">Online restore of filegroup `B`.</span></span>  
  
     <span data-ttu-id="6a84c-128">Los archivos del grupo de archivos `B` se restauran en cualquier momento a partir de este momento.</span><span class="sxs-lookup"><span data-stu-id="6a84c-128">Files in filegroup `B` are restored any time thereafter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6a84c-129">La copia de seguridad del grupo de archivos `B` se realizó después de cambiar el grupo a solo lectura, por lo que no es necesario poner al día estos archivos.</span><span class="sxs-lookup"><span data-stu-id="6a84c-129">The backup of filegroup `B` was taken after the filegroup became read-only; therefore, these files do not have to be rolled forward.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="6a84c-130">Todos los grupos de archivos están ahora en línea.</span><span class="sxs-lookup"><span data-stu-id="6a84c-130">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="6a84c-131">Otros ejemplos</span><span class="sxs-lookup"><span data-stu-id="6a84c-131">Additional Examples</span></span>  
  
-   [<span data-ttu-id="6a84c-132">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="6a84c-132">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="6a84c-133">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="6a84c-133">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="6a84c-134">Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="6a84c-134">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="6a84c-135">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="6a84c-135">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="6a84c-136">Ejemplo: restauración con conexión de un archivo de lectura/escritura &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="6a84c-136">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="6a84c-137">Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="6a84c-137">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="6a84c-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6a84c-138">See Also</span></span>  
 <span data-ttu-id="6a84c-139">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6a84c-139">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="6a84c-140">[Restauración con conexión &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6a84c-140">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="6a84c-141">[Aplicar copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6a84c-141">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="6a84c-142">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6a84c-142">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="6a84c-143">Restauraciones por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6a84c-143">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
