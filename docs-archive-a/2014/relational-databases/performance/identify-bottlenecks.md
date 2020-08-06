---
title: Identificar los cuellos de botella | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- resource bottlenecks [SQL Server]
- database monitoring [SQL Server], bottlenecks
- performance [SQL Server], bottlenecks
- tuning databases [SQL Server], bottlenecks
- monitoring server performance [SQL Server], bottlenecks
- monitoring performance [SQL Server], bottlenecks
- database performance [SQL Server], bottlenecks
- server performance [SQL Server], bottlenecks
- bottlenecks [SQL Server]
- identifying bottlenecks [SQL Server]
ms.assetid: db079e65-ee80-4105-aec9-f8230d0d6635
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e941b3f4a1185177cef007eb6a02a71ae1adece7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744649"
---
# <a name="identify-bottlenecks"></a><span data-ttu-id="c7b70-102">Identificar los cuellos de botella</span><span class="sxs-lookup"><span data-stu-id="c7b70-102">Identify Bottlenecks</span></span>
  <span data-ttu-id="c7b70-103">El acceso simultáneo a recursos compartidos causa cuellos de botella.</span><span class="sxs-lookup"><span data-stu-id="c7b70-103">Simultaneous access to shared resources causes bottlenecks.</span></span> <span data-ttu-id="c7b70-104">En general, los cuellos de botella están presentes en todos los sistemas de software y son inevitables.</span><span class="sxs-lookup"><span data-stu-id="c7b70-104">In general, bottlenecks are present in every software system and are inevitable.</span></span> <span data-ttu-id="c7b70-105">Sin embargo, la demanda excesiva de recursos compartidos causa un tiempo de respuesta largo, y debe identificarse y corregirse.</span><span class="sxs-lookup"><span data-stu-id="c7b70-105">However, excessive demands on shared resources cause poor response time and must be identified and tuned.</span></span>  
  
 <span data-ttu-id="c7b70-106">Entre las causas de estos cuellos de botella se incluyen:</span><span class="sxs-lookup"><span data-stu-id="c7b70-106">Causes of bottlenecks include:</span></span>  
  
-   <span data-ttu-id="c7b70-107">Recursos insuficientes que requieren componentes adicionales o actualizados.</span><span class="sxs-lookup"><span data-stu-id="c7b70-107">Insufficient resources, requiring additional or upgraded components.</span></span>  
  
-   <span data-ttu-id="c7b70-108">Recursos del mismo tipo que no distribuyen de forma equilibrada las cargas de trabajo; por ejemplo, cuando un recurso monopoliza un disco.</span><span class="sxs-lookup"><span data-stu-id="c7b70-108">Resources of the same type among which workloads are not distributed evenly; for example, one disk is being monopolized.</span></span>  
  
-   <span data-ttu-id="c7b70-109">Recursos que funcionan incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="c7b70-109">Malfunctioning resources.</span></span>  
  
-   <span data-ttu-id="c7b70-110">Recursos mal configurados.</span><span class="sxs-lookup"><span data-stu-id="c7b70-110">Incorrectly configured resources.</span></span>  
  
## <a name="analyzing-bottlenecks"></a><span data-ttu-id="c7b70-111">Analizar cuellos de botella</span><span class="sxs-lookup"><span data-stu-id="c7b70-111">Analyzing Bottlenecks</span></span>  
 <span data-ttu-id="c7b70-112">La duración excesiva de varios eventos es un indicador de cuello de botella que puede corregirse.</span><span class="sxs-lookup"><span data-stu-id="c7b70-112">Excessive durations for various events are indicators of bottlenecks that can be tuned.</span></span>  
  
 <span data-ttu-id="c7b70-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c7b70-113">For example:</span></span>  
  
-   <span data-ttu-id="c7b70-114">Otros componentes pueden evitar que la carga alcance este componente, lo que aumenta el tiempo que se tarda en completar la carga.</span><span class="sxs-lookup"><span data-stu-id="c7b70-114">Some other component may prevent the load from reaching this component thereby increasing the time to complete the load.</span></span>  
  
-   <span data-ttu-id="c7b70-115">Las solicitudes de cliente pueden tardar más tiempo debido a una congestión de la red.</span><span class="sxs-lookup"><span data-stu-id="c7b70-115">Client requests may take longer due to network congestion.</span></span>  
  
 <span data-ttu-id="c7b70-116">A continuación se indican cinco áreas clave que hay que supervisar para realizar un seguimiento del rendimiento del servidor e identificar cuellos de botella.</span><span class="sxs-lookup"><span data-stu-id="c7b70-116">Following are five key areas to monitor when tracking server performance to identify bottlenecks.</span></span>  
  
|<span data-ttu-id="c7b70-117">Posible área del cuello de botella</span><span class="sxs-lookup"><span data-stu-id="c7b70-117">Possible bottleneck area</span></span>|<span data-ttu-id="c7b70-118">Efectos en el servidor</span><span class="sxs-lookup"><span data-stu-id="c7b70-118">Effects on the server</span></span>|  
|------------------------------|---------------------------|  
|<span data-ttu-id="c7b70-119">Uso de la memoria</span><span class="sxs-lookup"><span data-stu-id="c7b70-119">Memory usage</span></span>|<span data-ttu-id="c7b70-120">Si no se asignó o no hay disponible suficiente memoria para Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , el rendimiento disminuirá.</span><span class="sxs-lookup"><span data-stu-id="c7b70-120">Insufficient memory allocated or available to Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] degrades performance.</span></span> <span data-ttu-id="c7b70-121">Los datos se deben leer en el disco, y no directamente en la caché de datos.</span><span class="sxs-lookup"><span data-stu-id="c7b70-121">Data must be read from the disk rather than directly from the data cache.</span></span> <span data-ttu-id="c7b70-122">Los sistemas operativos Microsoft Windows realizan una paginación excesiva intercambiando datos con el disco cuando son necesarias las páginas.</span><span class="sxs-lookup"><span data-stu-id="c7b70-122">Microsoft Windows operating systems perform excessive paging by swapping data to and from the disk as the pages are needed.</span></span>|  
|<span data-ttu-id="c7b70-123">Uso de CPU</span><span class="sxs-lookup"><span data-stu-id="c7b70-123">CPU utilization</span></span>|<span data-ttu-id="c7b70-124">Un uso excesivo continuo de la CPU puede indicar que las consultas de [!INCLUDE[tsql](../../includes/tsql-md.md)] deben optimizarse o que es necesaria una actualización de la CPU.</span><span class="sxs-lookup"><span data-stu-id="c7b70-124">A chronically high CPU utilization rate may indicate that [!INCLUDE[tsql](../../includes/tsql-md.md)] queries need to be tuned or that a CPU upgrade is needed.</span></span>|  
|<span data-ttu-id="c7b70-125">Entrada/salida (E/S) de disco</span><span class="sxs-lookup"><span data-stu-id="c7b70-125">Disk input/output (I/O)</span></span>|[!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="c7b70-126">consultas se pueden optimizar para reducir la E/S innecesaria; por ejemplo, mediante el uso de índices.</span><span class="sxs-lookup"><span data-stu-id="c7b70-126">queries can be tuned to reduce unnecessary I/O; for example, by employing indexes.</span></span>|  
|<span data-ttu-id="c7b70-127">Conexiones de usuario</span><span class="sxs-lookup"><span data-stu-id="c7b70-127">User connections</span></span>|<span data-ttu-id="c7b70-128">Puede haber demasiados usuarios obteniendo acceso al servidor de forma simultánea, lo que disminuye el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c7b70-128">Too many users may be accessing the server simultaneously causing performance degradation.</span></span>|  
|<span data-ttu-id="c7b70-129">Bloqueos de cierre</span><span class="sxs-lookup"><span data-stu-id="c7b70-129">Blocking locks</span></span>|<span data-ttu-id="c7b70-130">Las aplicaciones diseñadas incorrectamente pueden causar simultaneidad de obstáculos y bloqueos, lo que genera tiempos de respuesta más largos y un menor rendimiento de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="c7b70-130">Incorrectly designed applications can cause locks and hamper concurrency, thus causing longer response times and lower transaction throughput rates.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7b70-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c7b70-131">See Also</span></span>  
 <span data-ttu-id="c7b70-132">[Supervisar el uso de la CPU](../performance-monitor/monitor-cpu-usage.md) </span><span class="sxs-lookup"><span data-stu-id="c7b70-132">[Monitor CPU Usage](../performance-monitor/monitor-cpu-usage.md) </span></span>  
 <span data-ttu-id="c7b70-133">[Supervisar el uso del disco](../performance-monitor/monitor-disk-usage.md) </span><span class="sxs-lookup"><span data-stu-id="c7b70-133">[Monitor Disk Usage](../performance-monitor/monitor-disk-usage.md) </span></span>  
 <span data-ttu-id="c7b70-134">[Supervisar el uso de la memoria](../performance-monitor/monitor-memory-usage.md) </span><span class="sxs-lookup"><span data-stu-id="c7b70-134">[Monitor Memory Usage](../performance-monitor/monitor-memory-usage.md) </span></span>  
 <span data-ttu-id="c7b70-135">[General Statistics (objeto de SQL Server)](../performance-monitor/sql-server-general-statistics-object.md) </span><span class="sxs-lookup"><span data-stu-id="c7b70-135">[SQL Server, General Statistics Object](../performance-monitor/sql-server-general-statistics-object.md) </span></span>  
 [<span data-ttu-id="c7b70-136">Locks (objeto de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c7b70-136">SQL Server, Locks Object</span></span>](../performance-monitor/sql-server-locks-object.md)  
  
  
