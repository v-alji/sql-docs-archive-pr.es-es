---
title: 'Ejemplo: Restauración en línea de un archivo de lectura/escritura (modelo de recuperación completa) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- online restores [SQL Server], full recovery model
- restore sequences [SQL Server], online
ms.assetid: 0dbeda81-1464-44ba-9011-914900096368
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5b99a3d97644c2a5f104173457f30fc5b3fd7188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663537"
---
# <a name="example-online-restore-of-a-read-write-file-full-recovery-model"></a><span data-ttu-id="fbc13-102">Ejemplo: Restauración en línea de un archivo de lectura/escritura (modelo de recuperación completa)</span><span class="sxs-lookup"><span data-stu-id="fbc13-102">Example: Online Restore of a Read-Write File (Full Recovery Model)</span></span>
  <span data-ttu-id="fbc13-103">Este tema solo es de interés para las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contengan varios archivos o grupos de archivos con el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="fbc13-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="fbc13-104">En este ejemplo, una base de datos llamada `adb`, que utiliza el modelo de recuperación completa, contiene tres grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="fbc13-104">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="fbc13-105">El grupo de archivos `A` es de lectura/escritura, mientras que los grupos de archivos `B` y `C` son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="fbc13-105">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="fbc13-106">Inicialmente, todos los grupos de archivos están en línea.</span><span class="sxs-lookup"><span data-stu-id="fbc13-106">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="fbc13-107">El archivo `a1` del grupo de archivos `A` está dañado y el administrador de la base de datos decide restaurarlo con la base de datos en línea.</span><span class="sxs-lookup"><span data-stu-id="fbc13-107">File `a1` in filegroup `A` appears to be damaged, and the database administrator decides to restore it while the database remains online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fbc13-108">Con el modelo de recuperación simple no se puede realizar una restauración en línea de datos de lectura/escritura.</span><span class="sxs-lookup"><span data-stu-id="fbc13-108">Under the simple recovery model, online restore of read/write data is not allowed.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="fbc13-109">Secuencias de restauración</span><span class="sxs-lookup"><span data-stu-id="fbc13-109">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fbc13-110">La sintaxis de un flujo de restauración en línea es la misma que la de un flujo de restauración sin conexión.</span><span class="sxs-lookup"><span data-stu-id="fbc13-110">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="fbc13-111">Restauración en línea del archivo `a1`.</span><span class="sxs-lookup"><span data-stu-id="fbc13-111">Online restore of file `a1`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILE='a1' FROM backup   
    WITH NORECOVERY;  
    ```  
  
     <span data-ttu-id="fbc13-112">En este momento, el archivo a1 se encuentra en el estado RESTORING, mientras que el grupo de archivos A está sin conexión.</span><span class="sxs-lookup"><span data-stu-id="fbc13-112">At this point, file a1 is in the RESTORING state, and filegroup A is offline.</span></span>  
  
2.  <span data-ttu-id="fbc13-113">Tras restaurar el archivo, el administrador de la base de datos realiza una nueva copia de seguridad de registros para asegurarse de capturar el momento en el que el archivo se quedó sin conexión.</span><span class="sxs-lookup"><span data-stu-id="fbc13-113">After restoring the file, the database administrator takes a new log backup to make sure that the point at which the file went offline is captured.</span></span>  
  
    ```  
    BACKUP LOG adb TO log_backup3;   
    ```  
  
3.  <span data-ttu-id="fbc13-114">Restauración en línea de las copias de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="fbc13-114">Online restore of log backups.</span></span>  
  
     <span data-ttu-id="fbc13-115">El administrador restaura todas las copias de seguridad de registros tomadas desde la copia de seguridad de archivos restaurada, finalizando con la última copia de seguridad de registros (*log_backup3*, tomada en el paso 2).</span><span class="sxs-lookup"><span data-stu-id="fbc13-115">The administrator restores all the log backups taken since the restored file backup, ending with the latest log backup (*log_backup3*, taken in step 2).</span></span> <span data-ttu-id="fbc13-116">Tras restaurar la última copia de seguridad, la base de datos se recupera.</span><span class="sxs-lookup"><span data-stu-id="fbc13-116">After the last backup is restored, the database is recovered.</span></span>  
  
    ```  
    RESTORE LOG adb FROM log_backup1 WITH NORECOVERY;  
    RESTORE LOG adb FROM log_backup2 WITH NORECOVERY;  
    RESTORE LOG adb FROM log_backup3 WITH NORECOVERY;  
    RESTORE LOG adb WITH RECOVERY;  
    ```  
  
     <span data-ttu-id="fbc13-117">Ahora el archivo `a1` está en línea.</span><span class="sxs-lookup"><span data-stu-id="fbc13-117">File `a1` is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="fbc13-118">Otros ejemplos</span><span class="sxs-lookup"><span data-stu-id="fbc13-118">Additional Examples</span></span>  
  
-   [<span data-ttu-id="fbc13-119">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="fbc13-119">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="fbc13-120">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="fbc13-120">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="fbc13-121">Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="fbc13-121">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="fbc13-122">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="fbc13-122">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="fbc13-123">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="fbc13-123">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="fbc13-124">Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="fbc13-124">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="fbc13-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fbc13-125">See Also</span></span>  
 <span data-ttu-id="fbc13-126">[Restauración con conexión &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fbc13-126">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="fbc13-127">[Restauraciones por etapas &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fbc13-127">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="fbc13-128">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fbc13-128">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="fbc13-129">[Información general sobre restauración y recuperación &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fbc13-129">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="fbc13-130">[Aplicar copias de seguridad del registro de transacciones &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fbc13-130">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="fbc13-131">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fbc13-131">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
