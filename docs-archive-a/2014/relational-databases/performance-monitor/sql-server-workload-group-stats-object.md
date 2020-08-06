---
title: 'Objeto SQL Server: Estadísticas de grupo de cargas de trabajo | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Workload Group Stats object
- 'SQLServer: Workload Group Stats'
ms.assetid: ca20e4f6-50ec-4456-900d-87d280fde2b3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fb363803c562b305687e78e1315f1c4255041b1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671016"
---
# <a name="sql-server-workload-group-stats-object"></a><span data-ttu-id="1133c-102">Objeto SQL Server: Estadísticas de grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="1133c-102">SQL Server, Workload Group Stats Object</span></span>
  <span data-ttu-id="1133c-103">El objeto SQLServer:Estadísticas de grupo de cargas de trabajo contiene contadores de rendimiento que notifican información sobre las estadísticas de grupo de cargas de trabajo del regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="1133c-103">The SQLServer:Workload Group Stats object contains performance counters that report information about Resource Governor workload group statistics.</span></span>  
  
 <span data-ttu-id="1133c-104">Cada grupo de cargas de trabajo activo crea una instancia del objeto de rendimiento SQLServer:Estadísticas de grupo de cargas de trabajo que tiene el mismo nombre de instancia que el grupo de cargas de trabajo del regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="1133c-104">Each active workload group creates an instance of the SQLServer:Workload Group Stats performance object that has the same instance name as the Resource Governor workload group name.</span></span> <span data-ttu-id="1133c-105">En la tabla siguiente se describen los contadores admitidos en esta instancia.</span><span class="sxs-lookup"><span data-stu-id="1133c-105">The following table describes counters supported on this instance.</span></span>  
  
|<span data-ttu-id="1133c-106">Nombre del contador</span><span class="sxs-lookup"><span data-stu-id="1133c-106">Counter name</span></span>|<span data-ttu-id="1133c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1133c-107">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="1133c-108">Solicitudes en cola</span><span class="sxs-lookup"><span data-stu-id="1133c-108">Queued requests</span></span>|<span data-ttu-id="1133c-109">Número actual de solicitudes en cola que esperan ser recogidas.</span><span class="sxs-lookup"><span data-stu-id="1133c-109">The current number of queued requests that is waiting to be picked up.</span></span> <span data-ttu-id="1133c-110">Este número puede ser distinto de cero si se produce una limitación una vez alcanzado el límite GROUP_MAX_REQUESTS.</span><span class="sxs-lookup"><span data-stu-id="1133c-110">This count can be non-zero if throttling occurs after the GROUP_MAX_REQUESTS limit is reached.</span></span>|  
|<span data-ttu-id="1133c-111">Solicitudes activas</span><span class="sxs-lookup"><span data-stu-id="1133c-111">Active requests</span></span>|<span data-ttu-id="1133c-112">El número de solicitudes que están ejecutándose actualmente en este grupo de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1133c-112">The number of requests that are currently running in this workload group.</span></span> <span data-ttu-id="1133c-113">Este número debería ser equivalente al recuento de filas procedentes de sys.dm_exec_requests filtrado por identificador de grupo.</span><span class="sxs-lookup"><span data-stu-id="1133c-113">This should be equivalent to the count of rows from sys.dm_exec_requests filtered by group ID.</span></span>|  
|<span data-ttu-id="1133c-114">Solicitudes completadas/s</span><span class="sxs-lookup"><span data-stu-id="1133c-114">Requests completed/sec</span></span>|<span data-ttu-id="1133c-115">Número de solicitudes que se han completado en este grupo de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1133c-115">The number of requests that have completed in this workload group.</span></span> <span data-ttu-id="1133c-116">Este número es acumulativo.</span><span class="sxs-lookup"><span data-stu-id="1133c-116">This number is cumulative.</span></span>|  
|<span data-ttu-id="1133c-117">% de uso de CPU</span><span class="sxs-lookup"><span data-stu-id="1133c-117">CPU usage %</span></span>|<span data-ttu-id="1133c-118">Uso del ancho banda de CPU por parte de todas las solicitudes en este grupo de cargas de trabajo medidas en relación al equipo y normalizadas con respecto a todas las CPU del sistema.</span><span class="sxs-lookup"><span data-stu-id="1133c-118">The CPU bandwidth usage by all requests in this workload group measured relative to the computer and normalized to all the CPUs on the system.</span></span> <span data-ttu-id="1133c-119">Este valor cambiará a medida que la cantidad de CPU disponible para el proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] varíe.</span><span class="sxs-lookup"><span data-stu-id="1133c-119">This value will change as the amount of CPU available to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process changes.</span></span> <span data-ttu-id="1133c-120">No se normaliza respecto a lo que el proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recibe.</span><span class="sxs-lookup"><span data-stu-id="1133c-120">It is not normalized to what the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process receives.</span></span>|  
|<span data-ttu-id="1133c-121">Tiempo máximo de CPU por solicitud (ms)</span><span class="sxs-lookup"><span data-stu-id="1133c-121">Max request CPU time (ms)</span></span>|<span data-ttu-id="1133c-122">Tiempo de CPU máximo, en milisegundos, utilizado por una solicitud actualmente en ejecución en el grupo de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1133c-122">The maximum CPU time, in milliseconds, used by a request currently running in the workload group.</span></span>|  
|<span data-ttu-id="1133c-123">Solicitudes bloqueadas</span><span class="sxs-lookup"><span data-stu-id="1133c-123">Blocked requests</span></span>|<span data-ttu-id="1133c-124">Número actual de solicitudes bloqueadas en el grupo de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1133c-124">The current number of blocked requests in the workload group.</span></span> <span data-ttu-id="1133c-125">Este número se puede utilizar para determinar las características de la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1133c-125">This can be used to determine workload characteristics.</span></span>|  
|<span data-ttu-id="1133c-126">Concesiones con memoria reducida/s</span><span class="sxs-lookup"><span data-stu-id="1133c-126">Reduced memory grants/sec</span></span>|<span data-ttu-id="1133c-127">Número de consultas que obtienen una cantidad de concesiones de memoria por debajo de la cantidad ideal por segundo.</span><span class="sxs-lookup"><span data-stu-id="1133c-127">The number of queries that are getting less than ideal amount of memory grants per second.</span></span>|  
|<span data-ttu-id="1133c-128">Concesión máxima de memoria de solicitud (KB)</span><span class="sxs-lookup"><span data-stu-id="1133c-128">Max request memory grant (KB)</span></span>|<span data-ttu-id="1133c-129">Valor máximo de concesión de memoria, en kilobytes (KB), para una consulta.</span><span class="sxs-lookup"><span data-stu-id="1133c-129">The maximum value of memory grant, in kilobytes (KB), for a query.</span></span>|  
|<span data-ttu-id="1133c-130">Optimizaciones de consultas/s</span><span class="sxs-lookup"><span data-stu-id="1133c-130">Query optimizations/sec</span></span>|<span data-ttu-id="1133c-131">Número de optimizaciones de consultas por segundo que han tenido lugar en este grupo de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1133c-131">The number of query optimizations that have happened in this workload group per second.</span></span> <span data-ttu-id="1133c-132">Este número se puede utilizar para determinar las características de la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1133c-132">This can be used to determine workload characteristics.</span></span>|  
|<span data-ttu-id="1133c-133">Planes poco óptimos/s</span><span class="sxs-lookup"><span data-stu-id="1133c-133">Suboptimal plans/sec</span></span>|<span data-ttu-id="1133c-134">Número de planes poco óptimos que se generan en este grupo de cargas de trabajo por segundo.</span><span class="sxs-lookup"><span data-stu-id="1133c-134">The number of suboptimal plans that are generated in this workload group per second.</span></span>|  
|<span data-ttu-id="1133c-135">Subprocesos paralelos activos</span><span class="sxs-lookup"><span data-stu-id="1133c-135">Active parallel threads</span></span>|<span data-ttu-id="1133c-136">Recuento actual de uso de subprocesos paralelos.</span><span class="sxs-lookup"><span data-stu-id="1133c-136">The current count of parallel threads usage.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1133c-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1133c-137">See Also</span></span>  
 <span data-ttu-id="1133c-138">[Supervisar el uso de recursos &#40;Monitor de sistema&#41;](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="1133c-138">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="1133c-139">[Objeto SQL Server: Estadísticas de grupo de recursos de servidor](sql-server-resource-pool-stats-object.md) </span><span class="sxs-lookup"><span data-stu-id="1133c-139">[SQL Server, Resource Pool Stats Object](sql-server-resource-pool-stats-object.md) </span></span>  
 [<span data-ttu-id="1133c-140">Regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="1133c-140">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  