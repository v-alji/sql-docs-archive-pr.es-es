---
title: 'Ejemplo: restauración por etapas de la base de datos (modelo de recuperación simple) | Microsoft Docs'
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
ms.assetid: 9834b14a-4e56-4654-b190-c2a38624b6b4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69de84fa2ff3a853eb9926549ad4859d2f1ae38e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747644"
---
# <a name="example-piecemeal-restore-of-database-simple-recovery-model"></a><span data-ttu-id="9dbfd-102">Ejemplo: Restauración por etapas de base de datos (modelo de recuperación simple)</span><span class="sxs-lookup"><span data-stu-id="9dbfd-102">Example: Piecemeal Restore of Database (Simple Recovery Model)</span></span>
  <span data-ttu-id="9dbfd-103">En una secuencia de restauración por etapas restaura y recupera una base de datos en fases en el nivel del grupo de archivos, empezando con los grupos de archivos principales y todos los secundarios de lectura/escritura.</span><span class="sxs-lookup"><span data-stu-id="9dbfd-103">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, starting with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="9dbfd-104">En este ejemplo, la base de datos `adb` se restaura en un nuevo equipo después de un desastre.</span><span class="sxs-lookup"><span data-stu-id="9dbfd-104">In this example, database `adb` is restored to a new computer after a disaster.</span></span> <span data-ttu-id="9dbfd-105">La base de datos utiliza el modelo de recuperación simple.</span><span class="sxs-lookup"><span data-stu-id="9dbfd-105">The database is using the simple recovery model.</span></span> <span data-ttu-id="9dbfd-106">Antes del desastre, todos los grupos de archivos están en línea.</span><span class="sxs-lookup"><span data-stu-id="9dbfd-106">Before the disaster, all the filegroups are online.</span></span> <span data-ttu-id="9dbfd-107">Los grupos de archivos `A` y `C` son de lectura/escritura, y el grupo de archivos `B` es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="9dbfd-107">Filegroups `A` and `C` are read/write, and filegroup `B` is read-only.</span></span> <span data-ttu-id="9dbfd-108">El grupo de archivos `B` pasó a ser de solo lectura antes de la copia de seguridad parcial más reciente, que contiene el grupo de archivos principal y los grupos de archivos secundarios de lectura/escritura, `A` y `C`.</span><span class="sxs-lookup"><span data-stu-id="9dbfd-108">Filegroup `B` became read-only before the most recent partial backup, which contains the primary filegroup and the read/write secondary filegroups, `A` and `C`.</span></span> <span data-ttu-id="9dbfd-109">Después de que el grupo de archivos `B` pasara a ser de solo lectura, se realizó una copia de seguridad de archivos independiente del grupo de archivos `B` .</span><span class="sxs-lookup"><span data-stu-id="9dbfd-109">After filegroup `B` became read-only, a separate file backup of filegroup `B` was taken.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="9dbfd-110">Secuencias de restauración</span><span class="sxs-lookup"><span data-stu-id="9dbfd-110">Restore Sequences</span></span>  
  
1.  <span data-ttu-id="9dbfd-111">Restauración parcial del grupo de archivos principal y los grupos de archivos `A` y `C`.</span><span class="sxs-lookup"><span data-stu-id="9dbfd-111">Partial restore of the primary and filegroups `A` and `C`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='A',FILEGROUP='C'   
       FROM partial_backup   
       WITH PARTIAL, RECOVERY;  
  
    ```  
  
     <span data-ttu-id="9dbfd-112">En este momento, los grupos de archivos principal, `A` y `C` están en línea.</span><span class="sxs-lookup"><span data-stu-id="9dbfd-112">At this point, the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="9dbfd-113">Todos los archivos del grupo de archivos `B` están pendientes de recuperación y el grupo de archivos está sin conexión.</span><span class="sxs-lookup"><span data-stu-id="9dbfd-113">All files in filegroup `B` are recovery pending, and the filegroup is offline.</span></span>  
  
2.  <span data-ttu-id="9dbfd-114">Restauración con conexión del grupo de archivos `B`.</span><span class="sxs-lookup"><span data-stu-id="9dbfd-114">Online restore of filegroup `B`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup WITH RECOVERY;  
  
    ```  
  
     <span data-ttu-id="9dbfd-115">Todos los grupos de archivos están ahora en línea.</span><span class="sxs-lookup"><span data-stu-id="9dbfd-115">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="9dbfd-116">Otros ejemplos</span><span class="sxs-lookup"><span data-stu-id="9dbfd-116">Additional Examples</span></span>  
  
-   [<span data-ttu-id="9dbfd-117">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="9dbfd-117">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="9dbfd-118">Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="9dbfd-118">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="9dbfd-119">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="9dbfd-119">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="9dbfd-120">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="9dbfd-120">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="9dbfd-121">Ejemplo: restauración con conexión de un archivo de lectura/escritura &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="9dbfd-121">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="9dbfd-122">Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="9dbfd-122">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="9dbfd-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9dbfd-123">See Also</span></span>  
 <span data-ttu-id="9dbfd-124">[Restauración con conexión &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9dbfd-124">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="9dbfd-125">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9dbfd-125">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="9dbfd-126">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9dbfd-126">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="9dbfd-127">Restauraciones por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9dbfd-127">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
