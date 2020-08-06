---
title: Copias de seguridad parciales (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- partial backups [SQL Server]
- READ_WRITE_FILEGROUPS option
- database backups [SQL Server], about backing up databases
ms.assetid: fe6b6bb1-38d0-46c4-bab8-31df14e8999c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0c03cf2fb4d3af6fe87459e881e26c48cfacc232
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675473"
---
# <a name="partial-backups-sql-server"></a><span data-ttu-id="84943-102">Copias de seguridad parciales (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="84943-102">Partial Backups (SQL Server)</span></span>
  <span data-ttu-id="84943-103">Todos los modelos de recuperación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admiten copias de seguridad parciales, por lo que este tema es aplicable a todas las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="84943-103">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recovery models support partial backups, so this topic is relevant for all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="84943-104">Sin embargo, las copias de seguridad parciales están diseñadas para usarse con el modelo de recuperación simple a fin de mejorar la flexibilidad al realizar copias de seguridad de bases de datos de gran tamaño que contienen uno o varios grupos de archivos de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="84943-104">However, partial backups are designed for use under the simple recovery model to improve flexibility for backing up very large databases that contain one or more read-only filegroups.</span></span>  
  
 <span data-ttu-id="84943-105">Las copias de seguridad parciales resultan útiles cuando desea excluir grupos de archivos de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="84943-105">Partial backups are useful whenever you want to exclude read-only filegroups.</span></span> <span data-ttu-id="84943-106">Una *copia de seguridad parcial* es similar a una copia de seguridad de base de datos completa, pero no contiene todos los grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="84943-106">A *partial backup* resembles a full database backup, but a partial backup does not contain all the filegroups.</span></span> <span data-ttu-id="84943-107">En lugar de ello, en el caso de una base de datos de lectura y escritura, una copia de seguridad parcial contiene todos los datos del grupo de archivos principal, todos los grupos de archivos de lectura/escritura y, de manera opcional, uno o varios archivos de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="84943-107">Instead, for a read-write database, a partial backup contains the data in the primary filegroup, every read-write filegroup, and, optionally, one or more read-only files.</span></span> <span data-ttu-id="84943-108">Una copia de seguridad parcial de una base de datos de solo lectura contiene únicamente el grupo de archivos principal.</span><span class="sxs-lookup"><span data-stu-id="84943-108">A partial backup of a read-only database contains only the primary filegroup.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="84943-109">Si después de una copia de seguridad parcial se modifica el permiso de una base de datos de solo lectura a lectura y escritura, es posible que se creen grupos de archivos secundarios de lectura y escritura que no figuren en la copia de seguridad parcial.</span><span class="sxs-lookup"><span data-stu-id="84943-109">If a read-only database is changed to read/write after a partial backup, there might be read/write secondary filegroups that are not in the partial backup.</span></span> <span data-ttu-id="84943-110">En este caso, si intenta realizar una copia de seguridad diferencial parcial, el proceso producirá un error.</span><span class="sxs-lookup"><span data-stu-id="84943-110">In this case, if you try to take a differential partial backup, the backup fails.</span></span> <span data-ttu-id="84943-111">Antes de poder efectuar una copia de seguridad diferencial parcial de la base de datos, es preciso crear otra copia de seguridad parcial.</span><span class="sxs-lookup"><span data-stu-id="84943-111">Before you can take a differential partial backup of the database, you must take another partial backup.</span></span> <span data-ttu-id="84943-112">La nueva copia de seguridad parcial contiene todos los grupos de archivos secundarios de lectura /escritura y puede servir como base para las copias de seguridad diferenciales parciales.</span><span class="sxs-lookup"><span data-stu-id="84943-112">The new partial backup contains every read/write secondary filegroup and can serve as the base for differential partial backups.</span></span>  
  
 <span data-ttu-id="84943-113">Las copias de seguridad de archivos de los grupos de archivos de solo lectura se pueden combinar con copias de seguridad parciales.</span><span class="sxs-lookup"><span data-stu-id="84943-113">File backups of read-only filegroups can be combined with partial backups.</span></span> <span data-ttu-id="84943-114">Para obtener información sobre las copias de seguridad de archivos, vea [Copias de seguridad de archivos completas &#40;SQL Server&#41;](full-file-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="84943-114">For information about file backups, see [Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="84943-115">Una copia de seguridad parcial puede utilizarse como *base diferencial* para realizar copias de seguridad diferenciales parciales.</span><span class="sxs-lookup"><span data-stu-id="84943-115">A partial backup can serve as the *differential base* for differential partial backups.</span></span> <span data-ttu-id="84943-116">Para obtener más información, vea [Copias de seguridad diferenciales &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="84943-116">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="84943-117">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="84943-117">Related Tasks</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="84943-118">Las copias de seguridad parciales no son compatibles con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ni con el Asistente para planes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="84943-118">Partial backups are not supported by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the Maintenance Plan Wizard.</span></span>  
  
 <span data-ttu-id="84943-119">**Para crear una copia de seguridad parcial**</span><span class="sxs-lookup"><span data-stu-id="84943-119">**To create a partial backup**</span></span>  
  
-   <span data-ttu-id="84943-120">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) (READ_WRITE_FILEGROUPS; opción FILEGROUP, si es necesario)</span><span class="sxs-lookup"><span data-stu-id="84943-120">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) (READ_WRITE_FILEGROUPS; FILEGROUP option, if needed)</span></span>  
  
 <span data-ttu-id="84943-121">**Para usar una copia de seguridad parcial en una secuencia de restauración**</span><span class="sxs-lookup"><span data-stu-id="84943-121">**To use a partial backup in a restore sequence**</span></span>  
  
-   [<span data-ttu-id="84943-122">Ejemplo: restauración por etapas de la base de datos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="84943-122">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="84943-123">Ejemplo: restauración por etapas exclusiva para algunos grupos de archivos &#40;modelo de recuperación simple&#41;</span><span class="sxs-lookup"><span data-stu-id="84943-123">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="84943-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84943-124">See Also</span></span>  
 <span data-ttu-id="84943-125">[Información general de copia de seguridad &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="84943-125">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="84943-126">[Restauraciones de archivos &#40;modelo de recuperación simple&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="84943-126">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="84943-127">Restauraciones por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="84943-127">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
