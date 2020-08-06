---
title: Supervisión del uso de la CPU | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server], CPU usage
- tuning databases [SQL Server], CPU usage
- processors [SQL Server], monitoring usage
- database performance [SQL Server], CPU usage
- monitoring CPU usage [SQL Server]
- server performance [SQL Server], CPU usage
- database monitoring [SQL Server], CPU usage
- monitoring [SQL Server], CPU usage
- processors [SQL Server]
- CPU [SQL Server], monitoring
- monitoring server performance [SQL Server], CPU usage
ms.assetid: 2a02a3b6-07b2-4ad0-8a24-670414d19812
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f08d49348fd25593f27a87f2b0123f7ce43e35b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749246"
---
# <a name="monitor-cpu-usage"></a><span data-ttu-id="0afea-102">Supervisar el uso de la CPU</span><span class="sxs-lookup"><span data-stu-id="0afea-102">Monitor CPU Usage</span></span>
  <span data-ttu-id="0afea-103">Supervise una instancia de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periódicamente para determinar si los índices de uso de la CPU son normales.</span><span class="sxs-lookup"><span data-stu-id="0afea-103">Monitor an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically to determine whether CPU usage rates are within normal ranges.</span></span> <span data-ttu-id="0afea-104">Un índice de uso de la CPU constantemente alto puede indicar la necesidad de actualizar la CPU o de agregar varios procesadores.</span><span class="sxs-lookup"><span data-stu-id="0afea-104">A continually high rate of CPU usage may indicate the need to upgrade the CPU or add multiple processors.</span></span> <span data-ttu-id="0afea-105">Además, un uso alto de la CPU puede indicar que hay una aplicación mal optimizada o diseñada.</span><span class="sxs-lookup"><span data-stu-id="0afea-105">Alternatively, a high CPU usage rate may indicate a poorly tuned or designed application.</span></span> <span data-ttu-id="0afea-106">La optimización de la aplicación puede reducir el uso de la CPU.</span><span class="sxs-lookup"><span data-stu-id="0afea-106">Optimizing the application can lower CPU utilization.</span></span>  
  
 <span data-ttu-id="0afea-107">El contador **Procesador: % de tiempo de procesador** en el Monitor de sistema es la forma más eficaz de determinar el uso de la CPU.</span><span class="sxs-lookup"><span data-stu-id="0afea-107">An efficient way to determine CPU usage is to use the **Processor:% Processor Time** counter in System Monitor.</span></span> <span data-ttu-id="0afea-108">Este contador supervisa el tiempo que la CPU dedica a la ejecución de un subproceso que no está inactivo.</span><span class="sxs-lookup"><span data-stu-id="0afea-108">This counter monitors the amount of time the CPU spends executing a thread that is not idle.</span></span> <span data-ttu-id="0afea-109">Un estado continuado de entre el 80 y el 90 por ciento puede ser indicativo de que es necesario actualizar la CPU o bien agregar más procesadores.</span><span class="sxs-lookup"><span data-stu-id="0afea-109">A consistent state of 80 percent to 90 percent may indicate the need to upgrade your CPU or add more processors.</span></span> <span data-ttu-id="0afea-110">Para sistemas con múltiples procesadores, es necesario supervisar una instancia independiente de este contador para cada procesador.</span><span class="sxs-lookup"><span data-stu-id="0afea-110">For multiprocessor systems, monitor a separate instance of this counter for each processor.</span></span> <span data-ttu-id="0afea-111">Este valor representa la suma del tiempo de procesador en un procesador específico.</span><span class="sxs-lookup"><span data-stu-id="0afea-111">This value represents the sum of processor time on a specific processor.</span></span> <span data-ttu-id="0afea-112">Para determinar la media para todos los procesadores de impresión, utilice el contador **Sistema: % Tiempo total de procesador** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="0afea-112">To determine the average for all processors, use the **System: %Total Processor Time** counter instead.</span></span>  
  
 <span data-ttu-id="0afea-113">Para supervisar el uso del procesador también puede utilizar los siguientes contadores:</span><span class="sxs-lookup"><span data-stu-id="0afea-113">Optionally, you can also monitor the following counters to monitor processor usage:</span></span>  
  
-   <span data-ttu-id="0afea-114">**Procesador: % Tiempo privilegiado**</span><span class="sxs-lookup"><span data-stu-id="0afea-114">**Processor: % Privileged Time**</span></span>  
  
     <span data-ttu-id="0afea-115">Porcentaje de tiempo de procesador dedicado a la ejecución de comandos del kernel de Microsoft Windows, como el procesamiento de solicitudes de E/S de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0afea-115">Corresponds to the percentage of time the processor spends on execution of Microsoft Windows kernel commands, such as processing of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] I/O requests.</span></span> <span data-ttu-id="0afea-116">Si este contador es constantemente alto cuando los contadores **Disco físico** son altos, considere la posibilidad de instalar un subsistema de disco más rápido o eficaz.</span><span class="sxs-lookup"><span data-stu-id="0afea-116">If this counter is consistently high when the **Physical Disk** counters are high, consider installing a faster or more efficient disk subsystem.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0afea-117">Los diversos controladores de disco emplean distintos intervalos de tiempo de proceso del kernel.</span><span class="sxs-lookup"><span data-stu-id="0afea-117">Different disk controllers and drivers use different amounts of kernel processing time.</span></span> <span data-ttu-id="0afea-118">Los controladores eficaces utilizan menos tiempo privilegiado y dejan más tiempo de proceso disponible para aplicaciones del usuario, y aumentan así el rendimiento global.</span><span class="sxs-lookup"><span data-stu-id="0afea-118">Efficient controllers and drivers use less privileged time, leaving more processing time available for user applications, increasing overall throughput.</span></span>  
  
-   <span data-ttu-id="0afea-119">**Procesador: % Tiempo de usuario**</span><span class="sxs-lookup"><span data-stu-id="0afea-119">**Processor: %User Time**</span></span>  
  
     <span data-ttu-id="0afea-120">Porcentaje de tiempo que el procesador dedica a la ejecución de procesos de usuario, como por ejemplo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0afea-120">Corresponds to the percentage of time that the processor spends on executing user processes such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="0afea-121">**Sistema: Longitud de la cola del procesador**</span><span class="sxs-lookup"><span data-stu-id="0afea-121">**System: Processor Queue Length**</span></span>  
  
     <span data-ttu-id="0afea-122">Número de subprocesos en espera del tiempo del procesador.</span><span class="sxs-lookup"><span data-stu-id="0afea-122">Corresponds to the number of threads waiting for processor time.</span></span> <span data-ttu-id="0afea-123">Se produce un punto de congestión en el procesador cuando los subprocesos de un proceso requieren más ciclos de procesador que los disponibles.</span><span class="sxs-lookup"><span data-stu-id="0afea-123">A processor bottleneck develops when threads of a process require more processor cycles than are available.</span></span> <span data-ttu-id="0afea-124">Si bastantes procesos intentan utilizar el tiempo de procesador, puede que sea necesario instalar un procesador más rápido.</span><span class="sxs-lookup"><span data-stu-id="0afea-124">If more than a few processes attempt to utilize the processor's time, you might need to install a faster processor.</span></span> <span data-ttu-id="0afea-125">Si dispone de una sistema con múltiples procesadores, puede agregar un procesador.</span><span class="sxs-lookup"><span data-stu-id="0afea-125">Or, if you have a multiprocessor system, you could add a processor.</span></span>  
  
 <span data-ttu-id="0afea-126">Cuando examine el uso de los procesadores, tenga en cuenta el tipo de trabajo que realiza la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0afea-126">When you examine processor usage, consider the type of work that the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs.</span></span> <span data-ttu-id="0afea-127">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] realiza muchos cálculos, como consultas relativas a agregados o consultas enlazadas a memoria que no requieren E/S del disco, puede utilizarse el 100% del tiempo del procesador.</span><span class="sxs-lookup"><span data-stu-id="0afea-127">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs many calculations, such as queries involving aggregates or memory-bound queries that require no disk I/O, 100 percent of the processor's time can be used.</span></span> <span data-ttu-id="0afea-128">Si esto afecta negativamente al rendimiento de otras aplicaciones, pruebe a variar la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0afea-128">If this causes the performance of other applications to suffer, try changing the workload.</span></span> <span data-ttu-id="0afea-129">Por ejemplo, dedique el equipo a ejecutar la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0afea-129">For example, dedicate the computer to running the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0afea-130">Los valores de uso en torno al 100%, que indican que se están procesando muchas solicitudes de clientes, pueden mostrar que los procesos están en cola, en espera del tiempo del procesador y están causando un punto de congestión.</span><span class="sxs-lookup"><span data-stu-id="0afea-130">Usage rates around 100 percent, where many client requests are being processed, may indicate that processes are queuing up, waiting for processor time, and causing a bottleneck.</span></span> <span data-ttu-id="0afea-131">Para solucionar este problema, agregue procesadores de mayor velocidad.</span><span class="sxs-lookup"><span data-stu-id="0afea-131">Resolve the problem by adding faster processors.</span></span>  
  
  
