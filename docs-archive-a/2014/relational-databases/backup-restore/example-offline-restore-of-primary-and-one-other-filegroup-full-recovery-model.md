---
title: 'Ejemplo: restauración sin conexión del grupo de archivos principal y otro grupo de archivos (modelo de recuperación completa) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- offline restores [SQL Server]
- restore sequences [SQL Server], offline
ms.assetid: 7d6c50eb-dc84-4d66-855a-0b5f1bd89737
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6f845927fdd74fba476139fccbf9a5fa112d434e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676515"
---
# <a name="example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model"></a><span data-ttu-id="afbf9-102">Ejemplo: restauración sin conexión del grupo de archivo principal y de otro grupo de archivos (modelo de recuperación completa)</span><span class="sxs-lookup"><span data-stu-id="afbf9-102">Example: Offline Restore of Primary and One Other Filegroup (Full Recovery Model)</span></span>
  <span data-ttu-id="afbf9-103">Este tema solo es relevante para las bases de datos con el modelo de recuperación completa que contienen varios grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="afbf9-103">This topic is relevant only for databases under the full recovery model that contain multiple filegroups.</span></span>  
  
 <span data-ttu-id="afbf9-104">En este ejemplo, la base de datos `adb` contiene tres grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="afbf9-104">In this example, a database named `adb` contains three filegroups.</span></span> <span data-ttu-id="afbf9-105">Los grupos de archivos `A` y `C` son de lectura/escritura, y el grupo de archivos `B` es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="afbf9-105">Filegroups `A` and `C` are read/write, and filegroup `B` is read-only.</span></span> <span data-ttu-id="afbf9-106">Los grupos de archivos principal y `B` están dañados, pero los grupos de archivos `A` y `C` están intactos.</span><span class="sxs-lookup"><span data-stu-id="afbf9-106">The primary filegroup and filegroup `B` are damaged, but filegroups `A` and `C` are intact.</span></span> <span data-ttu-id="afbf9-107">Antes del desastre, todos los grupos de archivos estaban en línea.</span><span class="sxs-lookup"><span data-stu-id="afbf9-107">Before the disaster, all the filegroups were online.</span></span>  
  
 <span data-ttu-id="afbf9-108">El administrador de la base de datos decide restaurar y recuperar el grupo de archivos principal y el grupo de archivos `B`.</span><span class="sxs-lookup"><span data-stu-id="afbf9-108">The database administrator decides to restore and recover the primary filegroup and filegroup `B`.</span></span> <span data-ttu-id="afbf9-109">La base de datos está utilizando el modelo de recuperación completa, por lo que, antes de iniciar la restauración, debe crearse una copia del final del registro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="afbf9-109">The database is using the full recovery model; therefore, before the restore starts, a tail-log backup must be taken of the database.</span></span> <span data-ttu-id="afbf9-110">Cuando la base de datos se pone en línea, los grupos de archivos `A` y `C` se ponen en línea automáticamente.</span><span class="sxs-lookup"><span data-stu-id="afbf9-110">When the database comes on line, Filegroups `A` and `C` are automatically brought online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="afbf9-111">La secuencia de restauración sin conexión tiene menos pasos que la restauración en línea de un archivo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="afbf9-111">The offline restore sequence has fewer steps than an online restore of a read-only file.</span></span> <span data-ttu-id="afbf9-112">Para obtener un ejemplo, consulte [Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación completa&#41;](example-online-restore-of-a-read-only-file-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="afbf9-112">For an example, see [Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;](example-online-restore-of-a-read-only-file-full-recovery-model.md).</span></span> <span data-ttu-id="afbf9-113">Sin embargo, la base de datos completa estará sin conexión durante la secuencia.</span><span class="sxs-lookup"><span data-stu-id="afbf9-113">However, the whole database is offline for the duration of the sequence.</span></span>  
  
## <a name="tail-log-backup"></a><span data-ttu-id="afbf9-114">Copia del final del registro</span><span class="sxs-lookup"><span data-stu-id="afbf9-114">Tail-Log Backup</span></span>  
 <span data-ttu-id="afbf9-115">Antes de restaurar la base de datos, el administrador de la base de datos debe realizar una copia de seguridad de registros después del error.</span><span class="sxs-lookup"><span data-stu-id="afbf9-115">Before restoring the database, the database administrator must back up the tail of the log.</span></span> <span data-ttu-id="afbf9-116">Puesto que la base de datos está dañada, es necesario usar la opción NO_TRUNCATE al realizar la copia del final del registro:</span><span class="sxs-lookup"><span data-stu-id="afbf9-116">Because the database is damaged, creating the tail-log backup requires using the NO_TRUNCATE option:</span></span>  
  
```  
BACKUP LOG adb TO tailLogBackup   
   WITH NORECOVERY, NO_TRUNCATE  
```  
  
 <span data-ttu-id="afbf9-117">La copia del final del registro es la última copia de seguridad que se aplica en las secuencias de restauración siguientes.</span><span class="sxs-lookup"><span data-stu-id="afbf9-117">The tail-log backup is the last backup that is applied in the following restore sequences.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="afbf9-118">Secuencia de restauración</span><span class="sxs-lookup"><span data-stu-id="afbf9-118">Restore Sequence</span></span>  
 <span data-ttu-id="afbf9-119">Para restaurar los grupos de archivos principal y `B`, el administrador de la base de datos utiliza una secuencia de restauración sin la opción PARTIAL, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="afbf9-119">To restore the primary filegroup and filegroup `B`, the database administrator uses a restore sequence without the PARTIAL option, as follows:</span></span>  
  
```  
RESTORE DATABASE adb FILEGROUP='Primary' FROM backup1   
WITH NORECOVERY  
RESTORE DATABASE adb FILEGROUP='B' FROM backup2   
WITH NORECOVERY  
RESTORE LOG adb FROM backup3 WITH NORECOVERY  
RESTORE LOG adb FROM backup4 WITH NORECOVERY  
RESTORE LOG adb FROM backup5 WITH NORECOVERY  
RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
```  
  
 <span data-ttu-id="afbf9-120">Los archivos que no se restauran se ponen en línea automáticamente.</span><span class="sxs-lookup"><span data-stu-id="afbf9-120">The files that are not restored are automatically brought online.</span></span> <span data-ttu-id="afbf9-121">Todos los grupos de archivos están ahora en línea.</span><span class="sxs-lookup"><span data-stu-id="afbf9-121">All the filegroups are now online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afbf9-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="afbf9-122">See Also</span></span>  
 <span data-ttu-id="afbf9-123">[Restauración con conexión &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="afbf9-123">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="afbf9-124">[Restauraciones por etapas &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="afbf9-124">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="afbf9-125">[Restauraciones de archivos &#40;modelo de recuperación completa&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="afbf9-125">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="afbf9-126">[Aplicar copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="afbf9-126">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="afbf9-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="afbf9-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
