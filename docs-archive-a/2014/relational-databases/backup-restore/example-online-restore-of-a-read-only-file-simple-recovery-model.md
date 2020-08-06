---
title: 'Ejemplo: restauración en línea de un archivo de solo lectura (modelo de recuperación simple) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restore sequences [SQL Server], online
- online restores [SQL Server], simple recovery model
- simple recovery model [SQL Server], RESTORE examples
ms.assetid: 0c691fc6-9865-46a7-b055-8097424492d6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d84c920a2cb40866ba106b4d30d8e24c4caea611
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751222"
---
# <a name="example-online-restore-of-a-read-only-file-simple-recovery-model"></a><span data-ttu-id="fd3f5-102">Ejemplo: Restauración en línea de un archivo de solo lectura (modelo de recuperación simple)</span><span class="sxs-lookup"><span data-stu-id="fd3f5-102">Example: Online Restore of a Read-Only File (Simple Recovery Model)</span></span>
  <span data-ttu-id="fd3f5-103">Este tema solo es relevante para las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el modelo de recuperación simple que contienen un grupo de archivos de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the simple recovery model that contain a read-only filegroup.</span></span> <span data-ttu-id="fd3f5-104">El modelo de recuperación simple permite restaurar un archivo de solo lectura en línea si existe una copia de seguridad realizada después de que el archivo pasara a ser de solo lectura por última vez.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-104">Under the simple recovery model, a read-only file can be restored online if a file backup exists that was taken since the file became read-only for the last time.</span></span>  
  
 <span data-ttu-id="fd3f5-105">En este ejemplo, la base de datos `adb` contiene tres grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-105">In this example, a database named `adb` contains three filegroups.</span></span> <span data-ttu-id="fd3f5-106">El grupo de archivos `A` es de lectura/escritura, mientras que los grupos de archivos `B` y `C` son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-106">Filegroup `A` is read/write, and filegroups `B` and `C` are read-only.</span></span> <span data-ttu-id="fd3f5-107">Inicialmente, todos los grupos de archivos están en línea.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-107">Initially, all of the filegroups are online.</span></span> <span data-ttu-id="fd3f5-108">Se debe restaurar el archivo de solo lectura `B`del grupo de archivos `b1`.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-108">A read-only file in filegroup `B`, `b1`, has to be restored.</span></span> <span data-ttu-id="fd3f5-109">El administrador de la base de datos puede restaurarlo mediante una copia de seguridad realizada después de que el archivo pasara a ser de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-109">The database administrator can restore it by using a backup that was taken after the file became read-only.</span></span> <span data-ttu-id="fd3f5-110">Durante la restauración, el grupo de archivos `B` permanecerá sin conexión, pero el resto de la base de datos estará en línea.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-110">For the duration of the restore, filegroup `B` will be offline, but the remainder of the database will remain online.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="fd3f5-111">Secuencia de restauración</span><span class="sxs-lookup"><span data-stu-id="fd3f5-111">Restore Sequence</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd3f5-112">La sintaxis de un flujo de restauración en línea es la misma que la de un flujo de restauración sin conexión.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-112">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
 <span data-ttu-id="fd3f5-113">Para restaurar el archivo, el administrador de la base de datos utiliza la siguiente secuencia de restauración:</span><span class="sxs-lookup"><span data-stu-id="fd3f5-113">To restore the file, the database administrator uses the following restore sequence:</span></span>  
  
```  
RESTORE DATABASE adb FILE='b1' FROM filegroup_B_backup   
WITH RECOVERY  
```  
  
 <span data-ttu-id="fd3f5-114">Ahora el archivo está en línea.</span><span class="sxs-lookup"><span data-stu-id="fd3f5-114">The file is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="fd3f5-115">Otros ejemplos</span><span class="sxs-lookup"><span data-stu-id="fd3f5-115">Additional Examples</span></span>  
  
-   [<span data-ttu-id="fd3f5-116">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="fd3f5-116">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="fd3f5-117">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="fd3f5-117">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="fd3f5-118">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="fd3f5-118">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="fd3f5-119">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="fd3f5-119">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="fd3f5-120">Ejemplo: restauración con conexión de un archivo de lectura/escritura &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="fd3f5-120">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="fd3f5-121">Ejemplo: restauración con conexión de un archivo de solo lectura &#40;modelo de recuperación completa&#41;</span><span class="sxs-lookup"><span data-stu-id="fd3f5-121">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="fd3f5-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd3f5-122">See Also</span></span>  
 <span data-ttu-id="fd3f5-123">[Restauración con conexión &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fd3f5-123">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="fd3f5-124">[Restauraciones por etapas &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fd3f5-124">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="fd3f5-125">[Restauraciones de archivos &#40;modelo de recuperación simple&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="fd3f5-125">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="fd3f5-126">[Información general sobre restauración y recuperación &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fd3f5-126">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="fd3f5-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd3f5-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
