---
title: Backup Device (objeto de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Backup Device
- Backup Device object
ms.assetid: 52e7febf-d5e0-4674-945b-aacc40a9ad6e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e3126310ad31dcc153fc79508dbfaccf86f5da78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671497"
---
# <a name="sql-server-backup-device-object"></a><span data-ttu-id="d18ae-102">Backup Device (objeto de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d18ae-102">SQL Server, Backup Device Object</span></span>
  <span data-ttu-id="d18ae-103">El objeto **Backup Device** proporciona contadores para supervisar los dispositivos de copia de seguridad de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se utilizan para las operaciones de copias de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="d18ae-103">The **Backup Device** object provides counters to monitor Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup devices used for backup and restore operations.</span></span> <span data-ttu-id="d18ae-104">Supervise los dispositivos de copia de seguridad cuando desee determinar el rendimiento o el progreso de las operaciones de copias de seguridad y restauración en cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d18ae-104">Monitor backup devices when you want to determine the throughput or the progress and performance of your backup and restore operations on a per device basis.</span></span> <span data-ttu-id="d18ae-105">Para supervisar el rendimiento de la operación completa de copia de seguridad o restauración de la base de datos, use el contador **Rendimiento de copia de seguridad y restauración/** del objeto **Databases** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d18ae-105">To monitor the throughput of the entire database backup or restore operation, use the **Backup/Restore Throughput/sec** counter of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Databases** object.</span></span> <span data-ttu-id="d18ae-106">Para más información, vea [SQL Server, Databases Object](sql-server-databases-object.md).</span><span class="sxs-lookup"><span data-stu-id="d18ae-106">For more information, see [SQL Server, Databases Object](sql-server-databases-object.md).</span></span>  
  
 <span data-ttu-id="d18ae-107">En la siguiente tabla se describe el contador **Dispositivo de copia de seguridad** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d18ae-107">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Backup Device** counter.</span></span>  
  
|<span data-ttu-id="d18ae-108">Contadores de Dispositivo de copia de seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d18ae-108">SQL Server Backup Device counters</span></span>|<span data-ttu-id="d18ae-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d18ae-109">Description</span></span>|  
|---------------------------------------|-----------------|  
|<span data-ttu-id="d18ae-110">**Rendimiento del dispositivo en bytes/seg.**</span><span class="sxs-lookup"><span data-stu-id="d18ae-110">**Device Throughput Bytes/sec**</span></span>|<span data-ttu-id="d18ae-111">Rendimiento de las operaciones de lectura y escritura (en bytes por segundo) de un dispositivo de copia de seguridad utilizado para la copia de seguridad o la restauración de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="d18ae-111">Throughput of read and write operations (in bytes per second) for a backup device used when backing up or restoring databases.</span></span> <span data-ttu-id="d18ae-112">Este contador existe solo mientras se ejecuta la operación de copia de seguridad o restauración.</span><span class="sxs-lookup"><span data-stu-id="d18ae-112">This counter exists only while the backup or restore operation is executing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d18ae-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d18ae-113">See Also</span></span>  
 <span data-ttu-id="d18ae-114">[Dispositivos de copia de seguridad &#40;SQL Server&#41;](../backup-restore/backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d18ae-114">[Backup Devices &#40;SQL Server&#41;](../backup-restore/backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="d18ae-115">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="d18ae-115">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
