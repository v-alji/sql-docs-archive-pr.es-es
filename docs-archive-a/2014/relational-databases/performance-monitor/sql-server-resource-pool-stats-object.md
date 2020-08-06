---
title: 'Objeto SQL Server: Estadísticas de grupo de recursos de servidor | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Reosurce Pool Stats object
- 'SQLServer: Resource Pool Stats object'
ms.assetid: bb46e029-fcf9-4aeb-a066-be41e7668fb9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1c2ca8360e752146dac13e9cc6a3737ac2373cc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744659"
---
# <a name="sql-server-resource-pool-stats-object"></a><span data-ttu-id="c0f66-102">Objeto SQL Server: Estadísticas de grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="c0f66-102">SQL Server, Resource Pool Stats Object</span></span>
  <span data-ttu-id="c0f66-103">El objeto SQLServer:Estadísticas de grupo de recursos de servidor contiene contadores de rendimiento que notifican información sobre las estadísticas del grupo de recursos de servidor del regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="c0f66-103">The SQLServer:Resource Pool Stats object contains performance counters that report information about Resource Governor resource pool statistics.</span></span>  
  
 <span data-ttu-id="c0f66-104">Cada grupo de recursos de servidor activo crea una instancia del objeto de rendimiento SQLServer:Estadísticas de grupo de recursos de servidor que tiene el mismo nombre que el grupo de recursos de servidor del regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="c0f66-104">Each active resource pool creates an instance of the SQLServer:Resource Pool Stats performance object that has the same instance name as the Resource Governor resource pool name.</span></span> <span data-ttu-id="c0f66-105">En la tabla siguiente se describen los contadores admitidos en esta instancia.</span><span class="sxs-lookup"><span data-stu-id="c0f66-105">The following table describes counters supported on this instance.</span></span>  
  
|<span data-ttu-id="c0f66-106">Nombre del contador</span><span class="sxs-lookup"><span data-stu-id="c0f66-106">Counter name</span></span>|<span data-ttu-id="c0f66-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0f66-107">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="c0f66-108">% de uso de CPU</span><span class="sxs-lookup"><span data-stu-id="c0f66-108">CPU usage %</span></span>|<span data-ttu-id="c0f66-109">El uso de ancho banda de CPU por parte de todas las solicitudes en todos los grupos de cargas de trabajo pertenecientes a este grupo.</span><span class="sxs-lookup"><span data-stu-id="c0f66-109">The CPU bandwidth usage by all requests in all workload groups belonging to this pool.</span></span> <span data-ttu-id="c0f66-110">Este número se mide en relación al equipo y se normaliza respecto a todas las CPUs del sistema.</span><span class="sxs-lookup"><span data-stu-id="c0f66-110">This is measured relative to the computer and normalized to all CPUs on the system.</span></span> <span data-ttu-id="c0f66-111">Este valor cambiará a medida que la cantidad de CPU disponible para el proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] varíe.</span><span class="sxs-lookup"><span data-stu-id="c0f66-111">This value will change as the amount of CPU available to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process changes.</span></span> <span data-ttu-id="c0f66-112">No se normaliza respecto a lo que el proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recibe.</span><span class="sxs-lookup"><span data-stu-id="c0f66-112">It is not normalized to what the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process receives.</span></span>|  
|<span data-ttu-id="c0f66-113">% objetivo de uso de CPU</span><span class="sxs-lookup"><span data-stu-id="c0f66-113">CPU usage target %</span></span>|<span data-ttu-id="c0f66-114">Valor de destino del porcentaje de uso de CPU para el grupo de recursos de servidor según la configuración del grupo de recursos de servidor y la carga del sistema.</span><span class="sxs-lookup"><span data-stu-id="c0f66-114">The target value of CPU usage % for the resource pool based on the resource pool configuration settings and system load.</span></span>|  
|<span data-ttu-id="c0f66-115">% de efecto de control de CPU</span><span class="sxs-lookup"><span data-stu-id="c0f66-115">CPU control effect %</span></span>|<span data-ttu-id="c0f66-116">Efecto del regulador de recursos en el grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="c0f66-116">The effect of Resource Governor on the resource pool.</span></span> <span data-ttu-id="c0f66-117">Se calcula como (% de uso de la CPU) / (% de uso de la CPU sin regulador de recursos).</span><span class="sxs-lookup"><span data-stu-id="c0f66-117">Calculated as (CPU usage %) / (CPU usage % without Resource Governor.</span></span>|  
|<span data-ttu-id="c0f66-118">Destino de memoria de compilación (KB)</span><span class="sxs-lookup"><span data-stu-id="c0f66-118">Compile memory target (KB)</span></span>|<span data-ttu-id="c0f66-119">Destino del agente de memoria actual, en kilobytes (KB), para la compilación de consultas.</span><span class="sxs-lookup"><span data-stu-id="c0f66-119">The current memory broker target, in kilobytes (KB), for query compiles.</span></span>|  
|<span data-ttu-id="c0f66-120">Destino de memoria caché (KB)</span><span class="sxs-lookup"><span data-stu-id="c0f66-120">Cache memory target (KB)</span></span>|<span data-ttu-id="c0f66-121">Destino del agente de memoria actual, en kilobytes (KB), para la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="c0f66-121">The current memory broker target, in kilobytes (KB), for cache.</span></span>|  
|<span data-ttu-id="c0f66-122">Destino de memoria de ejecución de consultas (KB)</span><span class="sxs-lookup"><span data-stu-id="c0f66-122">Query exec memory target (KB)</span></span>|<span data-ttu-id="c0f66-123">Destino del agente de memoria actual, en kilobytes (KB), para la concesión de memoria de la ejecución de consultas.</span><span class="sxs-lookup"><span data-stu-id="c0f66-123">The current memory broker target, in kilobytes (KB), for query execution memory grant.</span></span> <span data-ttu-id="c0f66-124">Esta información también está disponible en [sys.dm_exec_query_memory_grants](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-memory-grants-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c0f66-124">This information is also available in [sys.dm_exec_query_memory_grants](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-memory-grants-transact-sql).</span></span>|  
|<span data-ttu-id="c0f66-125">Concesiones de memoria/s</span><span class="sxs-lookup"><span data-stu-id="c0f66-125">Memory grants/sec</span></span>|<span data-ttu-id="c0f66-126">Número de concesiones de memoria por segundo que han tenido lugar en este grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="c0f66-126">The number of memory grants occurring in this resource pool per second.</span></span>|  
|<span data-ttu-id="c0f66-127">Número de concesiones de memoria activas</span><span class="sxs-lookup"><span data-stu-id="c0f66-127">Active memory grants count</span></span>|<span data-ttu-id="c0f66-128">Número total actual de concesiones de memoria.</span><span class="sxs-lookup"><span data-stu-id="c0f66-128">Current total count of memory grants.</span></span> <span data-ttu-id="c0f66-129">Esta información también está disponible en [sys.dm_exec_query_memory_grants](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-memory-grants-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c0f66-129">This information is also available in [sys.dm_exec_query_memory_grants](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-memory-grants-transact-sql).</span></span>|  
|<span data-ttu-id="c0f66-130">Tiempos de espera agotados de concesiones de memoria/s</span><span class="sxs-lookup"><span data-stu-id="c0f66-130">Memory grant timeouts/sec</span></span>|<span data-ttu-id="c0f66-131">Número de tiempos de espera agotados de concesiones de memoria por segundo.</span><span class="sxs-lookup"><span data-stu-id="c0f66-131">The number of memory grant time-outs per second.</span></span>|  
|<span data-ttu-id="c0f66-132">Cantidad de concesiones de memoria activas (KB)</span><span class="sxs-lookup"><span data-stu-id="c0f66-132">Active memory grant amount (KB)</span></span>|<span data-ttu-id="c0f66-133">Cantidad total actual, en kilobytes (KB), de memoria concedida.</span><span class="sxs-lookup"><span data-stu-id="c0f66-133">The current total amount, in kilobytes (KB), of granted memory.</span></span> <span data-ttu-id="c0f66-134">Esta información también está disponible en [sys.dm_exec_query_resource_semaphores](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-resource-semaphores-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c0f66-134">This information is also available in [sys.dm_exec_query_resource_semaphores](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-resource-semaphores-transact-sql).</span></span>|  
|<span data-ttu-id="c0f66-135">Número de concesiones de memoria pendientes</span><span class="sxs-lookup"><span data-stu-id="c0f66-135">Pending memory grant count</span></span>|<span data-ttu-id="c0f66-136">Número de solicitudes de concesiones de memoria pendientes en las colas.</span><span class="sxs-lookup"><span data-stu-id="c0f66-136">The number of requests for memory grants pending in the queues.</span></span> <span data-ttu-id="c0f66-137">Esta información también está disponible en [sys.dm_exec_query_resource_semaphores](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-resource-semaphores-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c0f66-137">This information is also available in [sys.dm_exec_query_resource_semaphores](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-resource-semaphores-transact-sql).</span></span>|  
|<span data-ttu-id="c0f66-138">Memoria máxima (KB)</span><span class="sxs-lookup"><span data-stu-id="c0f66-138">Max memory (KB)</span></span>|<span data-ttu-id="c0f66-139">Cantidad máxima, en kilobytes (KB), de memoria que el grupo de recursos de servidor puede tener en función de la configuración del grupo de recursos de servidor y el estado del servidor.</span><span class="sxs-lookup"><span data-stu-id="c0f66-139">The maximum amount, in kilobytes (KB), of memory that the resource pool can have based on the resource pool settings and server state.</span></span>|  
|<span data-ttu-id="c0f66-140">Memoria usada (KB)</span><span class="sxs-lookup"><span data-stu-id="c0f66-140">Used memory (KB)</span></span>|<span data-ttu-id="c0f66-141">Cantidad de memoria utilizada, en kilobytes (KB), para el grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="c0f66-141">The amount of memory used, in kilobytes (KB), for the resource pool.</span></span>|  
|<span data-ttu-id="c0f66-142">Memoria de destino (KB)</span><span class="sxs-lookup"><span data-stu-id="c0f66-142">Target memory (KB)</span></span>|<span data-ttu-id="c0f66-143">Cantidad de destino, en kilobytes (KB), de memoria que el grupo de recursos de servidor trata de obtener en función de la configuración del grupo de recursos de servidor y el estado del servidor.</span><span class="sxs-lookup"><span data-stu-id="c0f66-143">The target amount, in kilobytes (KB), of memory the resource pool is trying to obtain based on the resource pool settings and server state.</span></span>|  
|<span data-ttu-id="c0f66-144">E/S de lectura de disco/s</span><span class="sxs-lookup"><span data-stu-id="c0f66-144">Disk Read IO/sec</span></span>|<span data-ttu-id="c0f66-145">Número de operaciones de lectura del disco en el último segundo.</span><span class="sxs-lookup"><span data-stu-id="c0f66-145">Number of read operations from the disk in the last second.</span></span>|  
|<span data-ttu-id="c0f66-146">E/S de lectura de disco limitadas/s</span><span class="sxs-lookup"><span data-stu-id="c0f66-146">Disk Read IO Throttled/sec</span></span>|<span data-ttu-id="c0f66-147">Número de operaciones de lectura limitadas en el último segundo.</span><span class="sxs-lookup"><span data-stu-id="c0f66-147">Number of read operations throttled in the last second.</span></span>|  
|<span data-ttu-id="c0f66-148">Bytes de lectura de disco/s</span><span class="sxs-lookup"><span data-stu-id="c0f66-148">Disk Read Bytes/sec</span></span>|<span data-ttu-id="c0f66-149">Número de bytes leídos del disco en el último segundo.</span><span class="sxs-lookup"><span data-stu-id="c0f66-149">Number of bytes read from the disk in the last second.</span></span>|  
|<span data-ttu-id="c0f66-150">Promedio de E/S de lectura de disco (ms)</span><span class="sxs-lookup"><span data-stu-id="c0f66-150">Avg Disk Read IO (ms)</span></span>|<span data-ttu-id="c0f66-151">Tiempo promedio, en milisegundos, de una operación de lectura del disco.</span><span class="sxs-lookup"><span data-stu-id="c0f66-151">Average time, in milliseconds, of a read operation from the disk.</span></span>|  
|<span data-ttu-id="c0f66-152">E/S de escrituras en disco/s</span><span class="sxs-lookup"><span data-stu-id="c0f66-152">Disk Write IO/sec</span></span>|<span data-ttu-id="c0f66-153">Número de operaciones de escritura en el disco en el último segundo.</span><span class="sxs-lookup"><span data-stu-id="c0f66-153">Number of write operations to the disk in the last second.</span></span>|  
|<span data-ttu-id="c0f66-154">E/S de escritura en disco limitadas/s</span><span class="sxs-lookup"><span data-stu-id="c0f66-154">Disk Write IO Throttled/sec</span></span>|<span data-ttu-id="c0f66-155">Número de operaciones de escritura limitadas en el último segundo.</span><span class="sxs-lookup"><span data-stu-id="c0f66-155">Number of write operations throttled in the last second.</span></span>|  
|<span data-ttu-id="c0f66-156">Bytes de escritura en disco/s</span><span class="sxs-lookup"><span data-stu-id="c0f66-156">Disk Write Bytes/sec</span></span>|<span data-ttu-id="c0f66-157">Número de bytes escritos en el disco en el último segundo.</span><span class="sxs-lookup"><span data-stu-id="c0f66-157">Number of bytes written to the disk in the last second.</span></span>|  
|<span data-ttu-id="c0f66-158">Promedio de escrituras en disco (ms)</span><span class="sxs-lookup"><span data-stu-id="c0f66-158">Avg Disk Write IO (ms)</span></span>|<span data-ttu-id="c0f66-159">Tiempo promedio, en milisegundos, de una operación de escritura en el disco.</span><span class="sxs-lookup"><span data-stu-id="c0f66-159">Average time, in milliseconds, of a write operation to the disk.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0f66-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0f66-160">See Also</span></span>  
 <span data-ttu-id="c0f66-161">[Supervisar el uso de recursos &#40;Monitor de sistema&#41;](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="c0f66-161">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="c0f66-162">[Objeto SQL Server: Estadísticas de grupo de cargas de trabajo](sql-server-workload-group-stats-object.md) </span><span class="sxs-lookup"><span data-stu-id="c0f66-162">[SQL Server, Workload Group Stats Object](sql-server-workload-group-stats-object.md) </span></span>  
 [<span data-ttu-id="c0f66-163">Regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="c0f66-163">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  