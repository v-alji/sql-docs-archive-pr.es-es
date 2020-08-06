---
title: Uso de OLTP en memoria en un entorno de máquina virtual | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 27ec7eb3-3a24-41db-aa65-2f206514c6f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83cf785fbcd2df9449d61e328e3bf8e374a6656d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745961"
---
# <a name="using-in-memory-oltp-in-a-vm-environment"></a><span data-ttu-id="52450-102">Uso de OLTP en memoria en un entorno de máquina virtual</span><span class="sxs-lookup"><span data-stu-id="52450-102">Using In-Memory OLTP in a VM Environment</span></span>
  <span data-ttu-id="52450-103">La virtualización del servidor puede ayudar a reducir la inversión y los costos operativos de TI y aumentar la eficacia de TI con mejores procesos de aprovisionamiento, mantenimiento, disponibilidad, copia de seguridad y recuperación.</span><span class="sxs-lookup"><span data-stu-id="52450-103">Server virtualization can help you lower IT capital and operational costs and attain greater IT efficiency with improved application provisioning, maintenance, availability, and backup/recovery processes.</span></span> <span data-ttu-id="52450-104">Con los avances tecnológicos recientes, es más fácil consolidar cargas de trabajo de base de datos complejas gracias a la virtualización.</span><span class="sxs-lookup"><span data-stu-id="52450-104">With recent technological advances, complex database workloads can be more readily consolidated using virtualization.</span></span> <span data-ttu-id="52450-105">En este tema se tratan los procedimientos recomendados para el uso de [!INCLUDE[hek_1](../includes/hek-1-md.md)] en un entorno virtualizado.</span><span class="sxs-lookup"><span data-stu-id="52450-105">This topic covers best practices for using [!INCLUDE[hek_1](../includes/hek-1-md.md)] in a virtualized environment.</span></span>  
  
##  <a name="memory-pre-allocation"></a><a name="bkmk_memoryPreAllocation"></a><span data-ttu-id="52450-106">Asignación previa de memoria</span><span class="sxs-lookup"><span data-stu-id="52450-106">Memory pre-allocation</span></span>  
 <span data-ttu-id="52450-107">Respecto a la memoria en un entorno virtualizado, son aspectos esenciales un mejor rendimiento y mayor compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="52450-107">For memory in a virtualized environment, better performance and enhanced support are essential considerations.</span></span> <span data-ttu-id="52450-108">Debe ser capaz de asignar memoria rápidamente a las máquinas virtuales en función de sus requisitos (cargas pico y fuera de horas pico) y asegurarse de que la memoria no se desperdicia.</span><span class="sxs-lookup"><span data-stu-id="52450-108">You must be able to both quickly allocate memory to virtual machines depending on their requirements (peak and off-peak loads) and ensure that the memory is not wasted.</span></span> <span data-ttu-id="52450-109">La característica de memoria dinámica de Hyper-V aumenta la agilidad de cómo se asigna y administra la memoria entre las máquinas virtuales que se ejecutan en un host.</span><span class="sxs-lookup"><span data-stu-id="52450-109">The Hyper-V Dynamic Memory feature increases agility in how the memory is allocated and managed between virtual machines running on a host.</span></span>  
  
 <span data-ttu-id="52450-110">Es necesario modificar algunas prácticas recomendadas para virtualizar y administrar [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cuando se virtualiza una base de datos con tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="52450-110">Some best practices for virtualizing and managing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] need to be modified when virtualizing a database with memory-optimized tables.</span></span> <span data-ttu-id="52450-111">Sin tablas optimizadas para memoria, dos de los procedimientos recomendados son:</span><span class="sxs-lookup"><span data-stu-id="52450-111">Without memory-optimized tables, two of the best practices are:</span></span>  
  
-   <span data-ttu-id="52450-112">Si se utiliza MIN_SERVER_MEMORY, es mejor asignar únicamente la cantidad de memoria que se necesita para que haya memoria suficiente para otros procesos (evitando de esta forma la paginación).</span><span class="sxs-lookup"><span data-stu-id="52450-112">If you use MIN_SERVER_MEMORY, it is better to assign only the amount of memory that is required so sufficient memory remains for other processes (thereby avoiding paging).</span></span>  
  
-   <span data-ttu-id="52450-113">No establecer un valor demasiado alto de asignación previa de memoria.</span><span class="sxs-lookup"><span data-stu-id="52450-113">Do not set the memory pre-allocation value too high.</span></span> <span data-ttu-id="52450-114">De lo contrario, puede que otros procesos no obtengan memoria suficiente cuando la necesiten, y esto puede producir paginación de memoria.</span><span class="sxs-lookup"><span data-stu-id="52450-114">Otherwise, other processes may not get sufficient memory at the time when they require it, and this can result in memory paging.</span></span>  
  
 <span data-ttu-id="52450-115">Si sigue los procedimientos anteriores para una base de datos con tablas optimizadas para memoria, el intento de restaurar y recuperar una base de datos podría dar lugar a que esta pasara a un estado "Pendiente de recuperación", incluso si hay memoria suficiente para recuperarla.</span><span class="sxs-lookup"><span data-stu-id="52450-115">If you follow the above practices for a database with memory-optimized tables, an attempt to restore and recover a database could result in the database being in a "Recovery Pending" state, even if you have sufficient memory to recover the database.</span></span> <span data-ttu-id="52450-116">El motivo es que, al iniciarse, [!INCLUDE[hek_2](../includes/hek-2-md.md)] pone los datos en memoria de forma mucho más dinámica que la forma en que la asignación de memoria dinámica asigna la memoria necesaria a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="52450-116">The reason for this is that, when starting up, [!INCLUDE[hek_2](../includes/hek-2-md.md)] brings data into memory more aggressively than dynamic memory allocation allocates memory to the database.</span></span>  
  
 <span data-ttu-id="52450-117">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="52450-117">**Resolution**</span></span>  
  
 <span data-ttu-id="52450-118">Para mitigar este problema, asigne previamente memoria suficiente a la base de datos para recuperar o reiniciar la base de datos; no especifique un valor mínimo confiando en que la memoria dinámica proporcionará memoria adicional cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="52450-118">To mitigate this, pre-allocate sufficient memory to the database to recover or restart the database, not a minimum value relying on dynamic memory to provide the additional memory when needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52450-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52450-119">See Also</span></span>  
 [<span data-ttu-id="52450-120">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="52450-120">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
