---
title: Supervisión del uso de la memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- tuning databases [SQL Server], memory
- monitoring server performance [SQL Server], memory usage
- isolating memory [SQL Server]
- paging rate [SQL Server]
- memory [SQL Server], monitoring usage
- monitoring [SQL Server], memory usage
- low-memory conditions
- database monitoring [SQL Server], memory usage
- available memory [SQL Server]
- page faults [SQL Server]
- monitoring performance [SQL Server], memory usage
- server performance [SQL Server], memory
ms.assetid: 1aee3933-a11c-4b87-91b7-32f5ea38c87f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1986d9576f9b067cad18f27d4febbf097ed52703
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749243"
---
# <a name="monitor-memory-usage"></a><span data-ttu-id="a6717-102">Supervisar el uso de la memoria</span><span class="sxs-lookup"><span data-stu-id="a6717-102">Monitor Memory Usage</span></span>
  <span data-ttu-id="a6717-103">Supervise una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periódicamente para confirmar que la utilización de la memoria se encuentra dentro de los intervalos normales.</span><span class="sxs-lookup"><span data-stu-id="a6717-103">Monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically to confirm that memory usage is within typical ranges.</span></span>  
  
 <span data-ttu-id="a6717-104">Para supervisar las condiciones de memoria insuficiente, utilice los contadores de objetos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a6717-104">To monitor for a low-memory condition, use the following object counters:</span></span>  
  
-   <span data-ttu-id="a6717-105">**Memoria: Bytes disponibles**</span><span class="sxs-lookup"><span data-stu-id="a6717-105">**Memory: Available Bytes**</span></span>  
  
-   <span data-ttu-id="a6717-106">**Memoria: Páginas/s**</span><span class="sxs-lookup"><span data-stu-id="a6717-106">**Memory: Pages/sec**</span></span>  
  
 <span data-ttu-id="a6717-107">El contador **Bytes disponibles** indica en bytes la memoria disponible actualmente para procesos.</span><span class="sxs-lookup"><span data-stu-id="a6717-107">The **Available Bytes** counter indicates how many bytes of memory are currently available for use by processes.</span></span> <span data-ttu-id="a6717-108">El contador **Páginas/s** indica el número de páginas que se han recuperado del disco debido a errores de página no recuperables o que se han escrito en disco para liberar espacio en el espacio de trabajo debido a errores de página.</span><span class="sxs-lookup"><span data-stu-id="a6717-108">The **Pages/sec** counter indicates the number of pages that either were retrieved from disk due to hard page faults or written to disk to free space in the working set due to page faults.</span></span>  
  
 <span data-ttu-id="a6717-109">Un valor bajo en el contador **Bytes disponibles** puede indicar una escasez general de memoria en el equipo o que un programa no está liberando memoria.</span><span class="sxs-lookup"><span data-stu-id="a6717-109">Low values for the **Available Bytes** counter can indicate that there is an overall shortage of memory on the computer or that an application is not releasing memory.</span></span> <span data-ttu-id="a6717-110">Un valor alto en el contador **Páginas/s** puede indicar una paginación excesiva.</span><span class="sxs-lookup"><span data-stu-id="a6717-110">A high rate for the **Pages/sec** counter could indicate excessive paging.</span></span> <span data-ttu-id="a6717-111">Supervise la **Memoria: Errores de página/s** para asegurarse de que la actividad del disco no está causada por la paginación.</span><span class="sxs-lookup"><span data-stu-id="a6717-111">Monitor the **Memory: Page Faults/sec** counter to make sure that the disk activity is not caused by paging.</span></span>  
  
 <span data-ttu-id="a6717-112">Una tasa baja de paginación (y por tanto, de errores de página) es normal, incluso si el equipo tiene mucha memoria disponible.</span><span class="sxs-lookup"><span data-stu-id="a6717-112">A low rate of paging (and hence page faults) is typical, even if the computer has plenty of available memory.</span></span> <span data-ttu-id="a6717-113">El Administrador de memoria virtual (VMM) de Microsoft Windows sustrae páginas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y otros procesos a medida que recorta los tamaños del espacio de trabajo para estos procesos,</span><span class="sxs-lookup"><span data-stu-id="a6717-113">The Microsoft Windows Virtual Memory Manager (VMM) takes pages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and other processes as it trims the working-set sizes of those processes.</span></span> <span data-ttu-id="a6717-114">lo que suele provocar errores de página.</span><span class="sxs-lookup"><span data-stu-id="a6717-114">This VMM activity tends to cause page faults.</span></span> <span data-ttu-id="a6717-115">Para determinar si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] u otro proceso son la causa de una paginación excesiva, supervise el contador **Proceso: Errores de página/s** para la instancia del proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6717-115">To determine whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or another process is the cause of excessive paging, monitor the **Process: Page Faults/sec** counter for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process instance.</span></span>  
  
 <span data-ttu-id="a6717-116">Para obtener más información acerca de cómo solucionar la paginación excesiva, vea la documentación del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="a6717-116">For more information about resolving excessive paging, see the Windows operating system documentation.</span></span>  
  
## <a name="isolating-memory-used-by-sql-server"></a><span data-ttu-id="a6717-117">Aislar la memoria que utiliza SQL Server</span><span class="sxs-lookup"><span data-stu-id="a6717-117">Isolating Memory Used by SQL Server</span></span>  
 <span data-ttu-id="a6717-118">De forma predeterminada, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cambia dinámicamente sus necesidades de memoria según los recursos del sistema disponibles.</span><span class="sxs-lookup"><span data-stu-id="a6717-118">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] changes its memory requirements dynamically, on the basis of available system resources.</span></span> <span data-ttu-id="a6717-119">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] necesita más memoria, consulta el sistema operativo para determinar si hay memoria física disponible y la utiliza.</span><span class="sxs-lookup"><span data-stu-id="a6717-119">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] needs more memory, it queries the operating system to determine whether free physical memory is available and uses the available memory.</span></span> <span data-ttu-id="a6717-120">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no necesita la memoria que tiene asignada actualmente, la libera para el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a6717-120">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not need the memory currently allocated to it, it releases the memory to the operating system.</span></span> <span data-ttu-id="a6717-121">En todo caso, el uso dinámico de la memoria puede anularse mediante las opciones de configuración de servidor **minservermemory**y **maxservermemory** .</span><span class="sxs-lookup"><span data-stu-id="a6717-121">However, you can override the option to dynamically use memory by using the **minservermemory**, and **maxservermemory** server configuration options.</span></span> <span data-ttu-id="a6717-122">Para obtener más información, vea el documento sobre las [opciones de memoria del servidor](../../database-engine/configure-windows/server-memory-server-configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="a6717-122">For more information, see [Server Memory Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md).</span></span>  
  
 <span data-ttu-id="a6717-123">Para supervisar la cantidad de memoria que utiliza [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , examine los siguientes contadores de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="a6717-123">To monitor the amount of memory that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses, examine the following performance counters:</span></span>  
  
-   <span data-ttu-id="a6717-124">**Proceso: espacio de trabajo**</span><span class="sxs-lookup"><span data-stu-id="a6717-124">**Process: Working Set**</span></span>  
  
-   <span data-ttu-id="a6717-125">**SQL Server: Administrador de búfer: frecuencia de aciertos de caché del búfer**</span><span class="sxs-lookup"><span data-stu-id="a6717-125">**SQL Server: Buffer Manager: Buffer Cache Hit Ratio**</span></span>  
  
-   <span data-ttu-id="a6717-126">**SQL Server: Administrador de búfer: páginas de base de datos**</span><span class="sxs-lookup"><span data-stu-id="a6717-126">**SQL Server: Buffer Manager: Database Pages**</span></span>  
  
-   <span data-ttu-id="a6717-127">**SQL Server: Administrador de memoria: memoria total del servidor (KB)**</span><span class="sxs-lookup"><span data-stu-id="a6717-127">**SQL Server: Memory Manager: Total Server Memory (KB)**</span></span>  
  
 <span data-ttu-id="a6717-128">El contador **Espacio de trabajo** muestra la cantidad de memoria que usa un proceso.</span><span class="sxs-lookup"><span data-stu-id="a6717-128">The **WorkingSet** counter shows the amount of memory that is used by a process.</span></span> <span data-ttu-id="a6717-129">Si este número es constantemente inferior a la cantidad de memoria establecida en las opciones del servidor **min server memory** y **max server memory** , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está configurado para utilizar más memoria de la que necesita.</span><span class="sxs-lookup"><span data-stu-id="a6717-129">If this number is consistently below the amount of memory that is set by the **min server memory** and **max server memory** server options, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use too much memory.</span></span>  
  
 <span data-ttu-id="a6717-130">El contador **Frecuencia de aciertos de caché del búfer** es específico de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a6717-130">The **Buffer Cache Hit Ratio** counter is specific to an application.</span></span> <span data-ttu-id="a6717-131">Sin embargo, es preferible un porcentaje del 90% o superior.</span><span class="sxs-lookup"><span data-stu-id="a6717-131">However, a rate of 90 percent or higher is desirable.</span></span> <span data-ttu-id="a6717-132">Agregue más memoria hasta que el valor sea superior al 90%,</span><span class="sxs-lookup"><span data-stu-id="a6717-132">Add more memory until the value is consistently greater than 90 percent.</span></span> <span data-ttu-id="a6717-133">lo que indica que se ha atendido más del 90% de todas las solicitudes de información de la caché de datos.</span><span class="sxs-lookup"><span data-stu-id="a6717-133">A value greater than 90 percent indicates that more than 90 percent of all requests for data were satisfied from the data cache.</span></span>  
  
 <span data-ttu-id="a6717-134">Si el valor del contador **Memoria total del servidor (KB)** siempre es alto en comparación con la cantidad de memoria física del equipo, puede que indique que se necesita más memoria.</span><span class="sxs-lookup"><span data-stu-id="a6717-134">If the **TotalServerMemory (KB)** counter is consistently high compared to the amount of physical memory in the computer, it may indicate that more memory is required.</span></span>  
  
## <a name="determining-current-memory-allocation"></a><span data-ttu-id="a6717-135">Determinar la asignación de memoria actual</span><span class="sxs-lookup"><span data-stu-id="a6717-135">Determining Current Memory Allocation</span></span>  
 <span data-ttu-id="a6717-136">La consulta siguiente devuelve información acerca de la memoria asignada actual.</span><span class="sxs-lookup"><span data-stu-id="a6717-136">The following query returns information about currently allocated memory.</span></span>  
  
```  
SELECT  
(physical_memory_in_use_kb/1024) AS Memory_usedby_Sqlserver_MB,  
(locked_page_allocations_kb/1024) AS Locked_pages_used_Sqlserver_MB,  
(total_virtual_address_space_kb/1024) AS Total_VAS_in_MB,  
process_physical_memory_low,  
process_virtual_memory_low  
FROM sys.dm_os_process_memory;  
```  
  
  
