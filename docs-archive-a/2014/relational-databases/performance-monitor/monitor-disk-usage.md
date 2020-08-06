---
title: Supervisión del uso del disco | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database monitoring [SQL Server], disk usage
- disks [SQL Server]
- monitoring performance [SQL Server], disk usage
- server performance [SQL Server], disk usage
- monitoring [SQL Server], disk activity
- excess paging [SQL Server]
- tuning databases [SQL Server], disk usage
- I/O [SQL Server], monitoring
- disks [SQL Server], monitoring activity
- isolating disk activity [SQL Server]
- database performance [SQL Server], disk usage
- monitoring server performance [SQL Server], disk usage
ms.assetid: 1525449c-ea7d-4222-b294-1ba1fe99c9ac
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 51479b024864322d34dc3b0208e29e93d7454184
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749244"
---
# <a name="monitor-disk-usage"></a><span data-ttu-id="6f3a6-102">Supervisar el uso del disco</span><span class="sxs-lookup"><span data-stu-id="6f3a6-102">Monitor Disk Usage</span></span>
  <span data-ttu-id="6f3a6-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa llamadas de entrada/salida (E/S) del sistema operativo Microsoft Windows para realizar las operaciones de lectura y escritura en el disco.</span><span class="sxs-lookup"><span data-stu-id="6f3a6-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses Microsoft Windows operating system input/output (I/O) calls to perform read and write operations on your disk.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6f3a6-104">administra el momento y el modo en que se realizan las operaciones de E/S de disco, pero el sistema operativo Windows realiza las operaciones de E/S subyacentes.</span><span class="sxs-lookup"><span data-stu-id="6f3a6-104">manages when and how disk I/O is performed, but the Windows operating system performs the underlying I/O operations.</span></span> <span data-ttu-id="6f3a6-105">El subsistema de E/S incluye el bus del sistema, tarjetas controladoras de disco, discos, unidades de cinta, la unidad de CD-ROM y muchos otros dispositivos de E/S.</span><span class="sxs-lookup"><span data-stu-id="6f3a6-105">The I/O subsystem includes the system bus, disk controller cards, disks, tape drives, CD-ROM drive, and many other I/O devices.</span></span> <span data-ttu-id="6f3a6-106">La E/S del disco es una causa frecuente de los atascos en un sistema.</span><span class="sxs-lookup"><span data-stu-id="6f3a6-106">Disk I/O is frequently the cause of bottlenecks in a system.</span></span>  
  
 <span data-ttu-id="6f3a6-107">La supervisión de la actividad del disco implica dos aspectos básicos:</span><span class="sxs-lookup"><span data-stu-id="6f3a6-107">Monitoring disk activity involves two areas of focus:</span></span>  
  
-   <span data-ttu-id="6f3a6-108">Supervisar la E/S del disco y detectar la paginación excesiva</span><span class="sxs-lookup"><span data-stu-id="6f3a6-108">Monitoring Disk I/O and Detecting Excess Paging</span></span>  
  
-   <span data-ttu-id="6f3a6-109">Aislar la actividad del disco que crea [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f3a6-109">Isolating Disk Activity That [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Creates</span></span>  
  
 <span data-ttu-id="6f3a6-110">Para obtener más información, vea [supervisar el uso del disco](https://social.technet.microsoft.com/wiki/contents/articles/monitoring-disk-usage.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6f3a6-110">For more information see, [Monitoring Disk Usage](https://social.technet.microsoft.com/wiki/contents/articles/monitoring-disk-usage.aspx)</span></span>  
  
  
