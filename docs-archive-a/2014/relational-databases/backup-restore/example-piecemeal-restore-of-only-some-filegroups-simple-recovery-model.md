---
title: 'Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos (modelo de recuperación simple) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- piecemeal restores [SQL Server], simple recovery model
- restore sequences [SQL Server], piecemeal
- simple recovery model [SQL Server], RESTORE examples
ms.assetid: d7ad026c-5355-4308-9560-0dc843940d4f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8254ac96a269b6fb433759e5a649bf9df1b7feac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751214"
---
# <a name="example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model"></a><span data-ttu-id="4d4f8-102">Ejemplo: Restauración por etapas exclusiva para algunos grupos de archivos (modelo de recuperación simple)</span><span class="sxs-lookup"><span data-stu-id="4d4f8-102">Example: Piecemeal Restore of Only Some Filegroups (Simple Recovery Model)</span></span>
  <span data-ttu-id="4d4f8-103">Este tema solo es relevante para las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el modelo de recuperación simple que contienen un grupo de archivos de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the simple recovery model that contain a read-only filegroup.</span></span>  
  
 <span data-ttu-id="4d4f8-104">En una secuencia de restauración por etapas restaura y recupera una base de datos en fases en el nivel del grupo de archivos, empezando con los grupos de archivos principales y todos los secundarios de lectura/escritura.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-104">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, beginning with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="4d4f8-105">En este ejemplo, una base de datos llamada `adb`, que utiliza el modelo de recuperación simple, contiene tres grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-105">In this example, a database named `adb`, which uses the simple recovery model, contains three filegroups.</span></span> <span data-ttu-id="4d4f8-106">El grupo de archivos `A` es de lectura/escritura, mientras que los grupos de archivos `B` y `C` son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-106">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="4d4f8-107">Inicialmente, todos los grupos de archivos están en línea.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-107">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="4d4f8-108">Parece que los grupos de archivos principal y `B` de la base de datos `adb` están dañados; por lo tanto, el administrador de la base de datos decide restaurarlos mediante una secuencia de restauración por etapas.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-108">The primary and filegroup `B` of database `adb` appear to be damaged; therefore, the database administrator decides to restore them by using a piecemeal restore sequence.</span></span> <span data-ttu-id="4d4f8-109">En un modelo de recuperación simple, todos los grupos de archivos de lectura/escritura deben restaurarse desde la misma copia de seguridad parcial.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-109">Under the simple recovery model, all read/write filegroups must be restored from the same partial backup.</span></span> <span data-ttu-id="4d4f8-110">Aunque el grupo de archivos `A` está intacto, debe restaurarse con el grupo de archivos principal para garantizar que sean coherentes (la base de datos se restaurará al momento definido por el final de la última copia de seguridad parcial).</span><span class="sxs-lookup"><span data-stu-id="4d4f8-110">Although filegroup `A` is intact, it must be restored with the primary filegroup to make sure that they are consistent (the database will be restored to the point in time defined by the end of the last partial backup).</span></span> <span data-ttu-id="4d4f8-111">El grupo de archivos `C` está intacto, pero debe recuperarlo para ponerlo en línea.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-111">Filegroup `C` is intact, but it must be recovered to bring it online.</span></span> <span data-ttu-id="4d4f8-112">El grupo de archivos `B`, aunque está dañado, contiene menos datos críticos que el grupo de archivos `C`; por tanto, `B` será el último en restaurarse.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-112">Filegroup `B`, although damaged, contains less critical data than Filegroup `C`; therefore, `B` will be restored last.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="4d4f8-113">Secuencias de restauración</span><span class="sxs-lookup"><span data-stu-id="4d4f8-113">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d4f8-114">La sintaxis de un flujo de restauración en línea es la misma que la de un flujo de restauración sin conexión.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-114">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="4d4f8-115">Restauración parcial de los grupos de archivos principal y `A` desde una copia de seguridad parcial.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-115">Partial restore of the primary and filegroup `A` from a partial backup.</span></span>  
  
    ```  
    RESTORE DATABASE adb READ_WRITE_FILEGROUPS FROM partial_backup   
    WITH PARTIAL, RECOVERY  
    ```  
  
     <span data-ttu-id="4d4f8-116">En este momento, los grupos de archivos principal y `A` están en línea.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-116">At this point the primary filegroup and filegroup `A` are online.</span></span> <span data-ttu-id="4d4f8-117">La recuperación de los archivos de los grupos `B` y `C` está pendiente, por lo que estos grupos de archivo están sin conexión.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-117">Files in filegroups `B` and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
2.  <span data-ttu-id="4d4f8-118">Recuperación en línea del grupo de archivos `C`.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-118">Online recovery of filegroup `C`.</span></span>  
  
     <span data-ttu-id="4d4f8-119">El grupo de archivos `C` es coherente porque la copia de seguridad parcial restaurada anteriormente se realizó después de que `C` pasara a ser de solo lectura, aunque la restauración hizo que la base de datos pasase a un punto anterior.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-119">Filegroup `C` is consistent because the partial backup that was restored above was taken after filegroup `C` became read-only, although the database was taken back in time by the restore.</span></span> <span data-ttu-id="4d4f8-120">El administrador de la base de datos recupera el grupo de archivos `C`, sin restaurarlo, y lo conecta.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-120">The database administrator recovers the filegroup `C`, without restoring it, to bring it online.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='C' WITH RECOVERY  
    ```  
  
     <span data-ttu-id="4d4f8-121">En este momento, los grupos de archivos principal, `A` y `C` están en línea.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-121">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="4d4f8-122">Los archivos del grupo B permanecen pendientes de recuperación, con el grupo de archivos sin conexión.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-122">Files in filegroupB remain recovery pending, with the filegroup offline.</span></span>  
  
3.  <span data-ttu-id="4d4f8-123">Restauración en línea del grupo de archivos `B.`</span><span class="sxs-lookup"><span data-stu-id="4d4f8-123">Online restore of filegroup `B.`</span></span>  
  
     <span data-ttu-id="4d4f8-124">Deben restaurarse los archivos del grupo de archivos `B` .</span><span class="sxs-lookup"><span data-stu-id="4d4f8-124">Files in filegroup `B` must be restored.</span></span> <span data-ttu-id="4d4f8-125">El administrador de la base de datos restaura la copia de seguridad del grupo de archivos `B` realizada después de que el grupo de archivos `B` pasara a ser de solo lectura y antes de la copia de seguridad parcial.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-125">The database administrator restores the backup of filegroup `B` taken after filegroup `B` became read-only and before the partial backup.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup   
    WITH RECOVERY  
    ```  
  
     <span data-ttu-id="4d4f8-126">Todos los grupos de archivos están ahora en línea.</span><span class="sxs-lookup"><span data-stu-id="4d4f8-126">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="4d4f8-127">Otros ejemplos</span><span class="sxs-lookup"><span data-stu-id="4d4f8-127">Additional Examples</span></span>  
  
-   [<span data-ttu-id="4d4f8-128">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="4d4f8-128">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="4d4f8-129">Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="4d4f8-129">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="4d4f8-130">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="4d4f8-130">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="4d4f8-131">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="4d4f8-131">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="4d4f8-132">Ejemplo: restauración con conexión de un archivo de lectura/escritura &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="4d4f8-132">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="4d4f8-133">Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="4d4f8-133">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="4d4f8-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d4f8-134">See Also</span></span>  
 <span data-ttu-id="4d4f8-135">[Restauración con conexión &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4d4f8-135">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="4d4f8-136">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4d4f8-136">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="4d4f8-137">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4d4f8-137">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="4d4f8-138">Restauraciones por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4d4f8-138">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
