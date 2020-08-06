---
title: Wait Statistics (objeto de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Wait Statistics object
- SQLServer:Wait Statistics
ms.assetid: cb7f917d-4291-4115-9b78-ee7692ebbb2d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5cfd2f1309cb118896ff7951b7f82feb38de60e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744652"
---
# <a name="sql-server-wait-statistics-object"></a><span data-ttu-id="82f63-102">Wait Statistics (objeto de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="82f63-102">SQL Server, Wait Statistics Object</span></span>
  <span data-ttu-id="82f63-103">El objeto de rendimiento de **SQLServer:Wait Statistics** contiene contadores de rendimiento que ofrecen información sobre el estado de la espera.</span><span class="sxs-lookup"><span data-stu-id="82f63-103">The **SQLServer:Wait Statistics** performance object contains performance counters that report information about wait status.</span></span>  
  
 <span data-ttu-id="82f63-104">La tabla incluida a continuación enumera los contadores que contiene el objeto de Wait Statistics.</span><span class="sxs-lookup"><span data-stu-id="82f63-104">The table below lists the counters that the Wait Statistics object contains.</span></span>  
  
|<span data-ttu-id="82f63-105">Contadores de Wait Statistics de SQL Server</span><span class="sxs-lookup"><span data-stu-id="82f63-105">SQL Server Wait Statistics counters</span></span>|<span data-ttu-id="82f63-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="82f63-106">Description</span></span>|  
|-----------------------------------------|-----------------|  
|<span data-ttu-id="82f63-107">**Esperas de bloqueo**</span><span class="sxs-lookup"><span data-stu-id="82f63-107">**Lock waits**</span></span>|<span data-ttu-id="82f63-108">Estadísticas para procesos que esperan en un bloqueo.</span><span class="sxs-lookup"><span data-stu-id="82f63-108">Statistics for processes waiting on a lock.</span></span>|  
|<span data-ttu-id="82f63-109">**Esperas de búfer de registro**</span><span class="sxs-lookup"><span data-stu-id="82f63-109">**Log buffer waits**</span></span>|<span data-ttu-id="82f63-110">Estadísticas para procesos que esperan que el búfer de registro esté disponible.</span><span class="sxs-lookup"><span data-stu-id="82f63-110">Statistics for processes waiting for log buffer to be available.</span></span>|  
|<span data-ttu-id="82f63-111">**Esperas de escritura en registro**</span><span class="sxs-lookup"><span data-stu-id="82f63-111">**Log write waits**</span></span>|<span data-ttu-id="82f63-112">Estadísticas para procesos que esperan que se escriba el búfer de registro.</span><span class="sxs-lookup"><span data-stu-id="82f63-112">Statistics for processes waiting for log buffer to be written.</span></span>|  
|<span data-ttu-id="82f63-113">**Esperas de cola de concesión de memoria**</span><span class="sxs-lookup"><span data-stu-id="82f63-113">**Memory grant queue waits**</span></span>|<span data-ttu-id="82f63-114">Estadísticas para procesos que esperan que una concesión de memoria esté disponible.</span><span class="sxs-lookup"><span data-stu-id="82f63-114">Statistics for processes waiting for memory grant to become available.</span></span>|  
|<span data-ttu-id="82f63-115">**Esperas de E/S de red**</span><span class="sxs-lookup"><span data-stu-id="82f63-115">**Network IO waits**</span></span>|<span data-ttu-id="82f63-116">Estadísticas relacionadas con la espera en E/S de red.</span><span class="sxs-lookup"><span data-stu-id="82f63-116">Statistics relevant to wait on network I/O.</span></span>|  
|<span data-ttu-id="82f63-117">**Esperas de bloqueos temporales distintos de páginas**</span><span class="sxs-lookup"><span data-stu-id="82f63-117">**Non-Page latch waits**</span></span>|<span data-ttu-id="82f63-118">Estadísticas relacionadas con bloqueos temporales distintos de páginas.</span><span class="sxs-lookup"><span data-stu-id="82f63-118">Statistics relevant to non-page latches.</span></span>|  
|<span data-ttu-id="82f63-119">**Esperas de bloqueos temporales de E/S de páginas**</span><span class="sxs-lookup"><span data-stu-id="82f63-119">**Page IO latch waits**</span></span>|<span data-ttu-id="82f63-120">Estadísticas relacionadas con bloqueos temporales de E/S de páginas.</span><span class="sxs-lookup"><span data-stu-id="82f63-120">Statistics relevant to page I/O latches.</span></span>|  
|<span data-ttu-id="82f63-121">**Esperas de bloqueos temporales de páginas**</span><span class="sxs-lookup"><span data-stu-id="82f63-121">**Page latch waits**</span></span>|<span data-ttu-id="82f63-122">Estadísticas relacionadas con bloqueos temporales de páginas, no incluidos los bloqueos temporales de E/S.</span><span class="sxs-lookup"><span data-stu-id="82f63-122">Statistics relevant to page latches, not including I/O latches.</span></span>|  
|<span data-ttu-id="82f63-123">**Esperas de objetos de memoria seguros para subprocesos**</span><span class="sxs-lookup"><span data-stu-id="82f63-123">**Thread-safe memory objects waits**</span></span>|<span data-ttu-id="82f63-124">Estadísticas para procesos que esperan en asignadores de memoria seguros para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="82f63-124">Statistics for processes waiting on thread-safe memory allocators.</span></span>|  
|<span data-ttu-id="82f63-125">**Esperas de propiedad de transacción**</span><span class="sxs-lookup"><span data-stu-id="82f63-125">**Transaction ownership waits**</span></span>|<span data-ttu-id="82f63-126">Estadísticas relacionadas con procesos que sincronizan el acceso a la transacción.</span><span class="sxs-lookup"><span data-stu-id="82f63-126">Statistics relevant to processes synchronizing access to transaction.</span></span>|  
|<span data-ttu-id="82f63-127">**Espera del objeto de trabajo**</span><span class="sxs-lookup"><span data-stu-id="82f63-127">**Wait for the worker**</span></span>|<span data-ttu-id="82f63-128">Estadísticas relacionadas con procesos que esperan que el objeto de trabajo esté disponible.</span><span class="sxs-lookup"><span data-stu-id="82f63-128">Statistics relevant to processes waiting for worker to become available.</span></span>|  
|<span data-ttu-id="82f63-129">**Esperas de sincronización de área de trabajo**</span><span class="sxs-lookup"><span data-stu-id="82f63-129">**Workspace synchronization waits**</span></span>|<span data-ttu-id="82f63-130">Estadísticas relacionadas con procesos que sincronizan el acceso al área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="82f63-130">Statistics relevant to processes synchronizing access to workspace.</span></span>|  
  
 <span data-ttu-id="82f63-131">Cada contador del objeto contiene las instancias siguientes:</span><span class="sxs-lookup"><span data-stu-id="82f63-131">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="82f63-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="82f63-132">Item</span></span>|<span data-ttu-id="82f63-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="82f63-133">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="82f63-134">**Tiempo promedio de espera (ms)**</span><span class="sxs-lookup"><span data-stu-id="82f63-134">**Average wait time (ms)**</span></span>|<span data-ttu-id="82f63-135">Tiempo promedio del tipo de espera seleccionado.</span><span class="sxs-lookup"><span data-stu-id="82f63-135">Average time for the selected type of wait.</span></span>|  
|<span data-ttu-id="82f63-136">**Tiempo de espera acumulado (ms) por segundo**</span><span class="sxs-lookup"><span data-stu-id="82f63-136">**Cumulative wait time (ms) per second**</span></span>|<span data-ttu-id="82f63-137">Tiempo de espera agregado por segundo para el tipo de espera seleccionado.</span><span class="sxs-lookup"><span data-stu-id="82f63-137">Aggregated wait time per second, for the selected type of wait.</span></span>|  
|<span data-ttu-id="82f63-138">**Espera en curso**</span><span class="sxs-lookup"><span data-stu-id="82f63-138">**Waits in progress**</span></span>|<span data-ttu-id="82f63-139">Número de procesos actualmente en espera en el tipo siguiente.</span><span class="sxs-lookup"><span data-stu-id="82f63-139">Number of processes currently waiting on the following type.</span></span>|  
|<span data-ttu-id="82f63-140">**Esperas iniciadas por segundo**</span><span class="sxs-lookup"><span data-stu-id="82f63-140">**Waits started per second**</span></span>|<span data-ttu-id="82f63-141">Número de esperas iniciadas por segundo del tipo de espera seleccionado.</span><span class="sxs-lookup"><span data-stu-id="82f63-141">Number of waits started per second of the selected type of wait.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82f63-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82f63-142">See Also</span></span>  
 [<span data-ttu-id="82f63-143">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="82f63-143">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
