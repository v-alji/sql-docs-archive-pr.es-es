---
title: Latches (objeto de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Latches object
- SQLServer:Latches
ms.assetid: 2393ea1c-2bf3-41c3-9f37-b9761144eeca
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6f49ac00114065e971c0893f9217ab883eb2d7f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669627"
---
# <a name="sql-server-latches-object"></a><span data-ttu-id="865a1-102">Latches (objeto de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="865a1-102">SQL Server, Latches Object</span></span>
  <span data-ttu-id="865a1-103">El objeto **SQLServer:Latches** en Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proporciona contadores para supervisar los bloqueos de recursos internos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , denominados bloqueos temporales.</span><span class="sxs-lookup"><span data-stu-id="865a1-103">The **SQLServer:Latches** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor internal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource locks called latches.</span></span> <span data-ttu-id="865a1-104">La supervisión de los bloqueos temporales para determinar la actividad de los usuarios y el uso de los recursos puede ayudar a identificar puntos de congestión en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="865a1-104">Monitoring the latches to determine user activity and resource usage can help you to identify performance bottlenecks.</span></span>  
  
 <span data-ttu-id="865a1-105">En esta tabla se describen los contadores de **bloqueos temporales** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="865a1-105">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Latches** counters.</span></span>  
  
|<span data-ttu-id="865a1-106">Contadores de bloqueos temporales de SQL Server</span><span class="sxs-lookup"><span data-stu-id="865a1-106">SQL Server Latches counters</span></span>|<span data-ttu-id="865a1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="865a1-107">Description</span></span>|  
|---------------------------------|-----------------|  
|<span data-ttu-id="865a1-108">**Promedio de tiempo de espera para los bloqueos temporales (ms)**</span><span class="sxs-lookup"><span data-stu-id="865a1-108">**Average Latch Wait Time (ms)**</span></span>|<span data-ttu-id="865a1-109">Promedio de tiempo de espera de los bloqueos temporales (en milisegundos) para solicitudes de bloqueos temporales que tuvieron que esperar.</span><span class="sxs-lookup"><span data-stu-id="865a1-109">Average latch wait time (in milliseconds) for latch requests that had to wait.</span></span>|  
|<span data-ttu-id="865a1-110">**Esperas de bloqueos temporales/seg.**</span><span class="sxs-lookup"><span data-stu-id="865a1-110">**Latch Waits/sec**</span></span>|<span data-ttu-id="865a1-111">Número de solicitudes de bloqueo temporal que no se concedieron inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="865a1-111">Number of latch requests that could not be granted immediately.</span></span>|  
|<span data-ttu-id="865a1-112">**Número de SuperLatches**</span><span class="sxs-lookup"><span data-stu-id="865a1-112">**Number of SuperLatches**</span></span>|<span data-ttu-id="865a1-113">Número de bloqueos temporales que actualmente son SuperLatches.</span><span class="sxs-lookup"><span data-stu-id="865a1-113">Number of latches that are currently SuperLatches.</span></span>|  
|<span data-ttu-id="865a1-114">**Degradaciones de SuperLatch/seg.**</span><span class="sxs-lookup"><span data-stu-id="865a1-114">**SuperLatch Demotions/sec**</span></span>|<span data-ttu-id="865a1-115">Número de SuperLatches degradados a bloqueos temporales normales en el último segundo transcurrido.</span><span class="sxs-lookup"><span data-stu-id="865a1-115">Number of SuperLatches that have been demoted to regular latches in the last second.</span></span>|  
|<span data-ttu-id="865a1-116">**Ascensos a SuperLatch/seg.**</span><span class="sxs-lookup"><span data-stu-id="865a1-116">**SuperLatch Promotions/sec**</span></span>|<span data-ttu-id="865a1-117">Número de bloqueos temporales ascendidos a SuperLatches en el último segundo transcurrido.</span><span class="sxs-lookup"><span data-stu-id="865a1-117">Number of latches that have been promoted to SuperLatches in the last second.</span></span>|  
|<span data-ttu-id="865a1-118">**Tiempo total de espera de los bloqueos temporales (ms)**</span><span class="sxs-lookup"><span data-stu-id="865a1-118">**Total Latch Wait Time (ms)**</span></span>|<span data-ttu-id="865a1-119">Tiempo total de espera para bloqueos temporales (en milisegundos) de las solicitudes de bloqueos temporales en el último segundo.</span><span class="sxs-lookup"><span data-stu-id="865a1-119">Total latch wait time (in milliseconds) for latch requests in the last second.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="865a1-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="865a1-120">See Also</span></span>  
 [<span data-ttu-id="865a1-121">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="865a1-121">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
