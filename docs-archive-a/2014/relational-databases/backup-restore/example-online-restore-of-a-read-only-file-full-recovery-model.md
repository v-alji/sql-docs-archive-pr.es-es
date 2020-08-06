---
title: 'Ejemplo: restauración en línea de un archivo de solo lectura (modelo de recuperación completa) | Microsoft Docs'
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
ms.assetid: 7ea2d2af-086f-48dc-9636-38dc194c7090
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f493c88d64e6ed22e44f33f1442ae581daa8ed4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751225"
---
# <a name="example-online-restore-of-a-read-only-file-full-recovery-model"></a><span data-ttu-id="69eb8-102">Ejemplo: Restauración en línea de un archivo de solo lectura (modelo de recuperación completa)</span><span class="sxs-lookup"><span data-stu-id="69eb8-102">Example: Online Restore of a Read-Only File (Full Recovery Model)</span></span>
  <span data-ttu-id="69eb8-103">Este tema solo es de interés para las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contengan varios archivos o grupos de archivos con el modelo de recuperación completa.</span><span class="sxs-lookup"><span data-stu-id="69eb8-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="69eb8-104">En este ejemplo, una base de datos llamada `adb`, que utiliza el modelo de recuperación completa, contiene tres grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="69eb8-104">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="69eb8-105">El grupo de archivos `A` es de lectura/escritura, mientras que los grupos de archivos `B` y `C` son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="69eb8-105">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="69eb8-106">Inicialmente, todos los grupos de archivos están en línea.</span><span class="sxs-lookup"><span data-stu-id="69eb8-106">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="69eb8-107">Se debe restaurar un archivo de solo lectura, `b1`, del grupo de archivos `B` de la base de datos `adb` .</span><span class="sxs-lookup"><span data-stu-id="69eb8-107">A read-only file, `b1`, in filegroup `B` of database `adb` has to be restored.</span></span> <span data-ttu-id="69eb8-108">Se realizó una copia de seguridad después de que el archivo pasó a ser de solo lectura, por lo que no es necesario realizar copias de seguridad de registros.</span><span class="sxs-lookup"><span data-stu-id="69eb8-108">A backup was taken since the file became read-only; therefore, log backups are not required.</span></span> <span data-ttu-id="69eb8-109">El grupo de archivos `B` está sin conexión durante la restauración, pero el resto de la base de datos sigue estando en línea.</span><span class="sxs-lookup"><span data-stu-id="69eb8-109">Filegroup `B` is offline for the duration of the restore, but the remainder of the database remains online.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="69eb8-110">Secuencia de restauración</span><span class="sxs-lookup"><span data-stu-id="69eb8-110">Restore Sequence</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="69eb8-111">La sintaxis de un flujo de restauración en línea es la misma que la de un flujo de restauración sin conexión.</span><span class="sxs-lookup"><span data-stu-id="69eb8-111">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
 <span data-ttu-id="69eb8-112">Para restaurar el archivo, el administrador de la base de datos utiliza la siguiente secuencia de restauración:</span><span class="sxs-lookup"><span data-stu-id="69eb8-112">To restore the file, the database administrator uses the following restore sequence:</span></span>  
  
```  
RESTORE DATABASE adb FILE='b1' FROM filegroup_B_backup  
WITH RECOVERY   
```  
  
 <span data-ttu-id="69eb8-113">Ahora el grupo de archivos B está en línea.</span><span class="sxs-lookup"><span data-stu-id="69eb8-113">Filegroup B is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="69eb8-114">Otros ejemplos</span><span class="sxs-lookup"><span data-stu-id="69eb8-114">Additional Examples</span></span>  
  
-   [<span data-ttu-id="69eb8-115">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="69eb8-115">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="69eb8-116">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="69eb8-116">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="69eb8-117">Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="69eb8-117">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="69eb8-118">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="69eb8-118">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="69eb8-119">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="69eb8-119">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="69eb8-120">Ejemplo: restauración con conexión de un archivo de lectura/escritura &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="69eb8-120">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="69eb8-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69eb8-121">See Also</span></span>  
 <span data-ttu-id="69eb8-122">[Restauración con conexión &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="69eb8-122">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="69eb8-123">[Información general sobre restauración y recuperación &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="69eb8-123">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="69eb8-124">[Restauraciones de archivos &#40;modelo de recuperación completa&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="69eb8-124">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="69eb8-125">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="69eb8-125">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
