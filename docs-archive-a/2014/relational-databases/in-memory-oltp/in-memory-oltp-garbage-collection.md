---
title: Recolección de elementos no utilizados de OLTP en memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 940140a7-4785-46fc-8bf4-151435dccd3c
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 23997d3664fb48902d2be08bbb22d2189c832298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749323"
---
# <a name="in-memory-oltp-garbage-collection"></a><span data-ttu-id="c320e-102">Recolección de elementos no utilizados de OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="c320e-102">In-Memory OLTP Garbage Collection</span></span>
  <span data-ttu-id="c320e-103">Una fila de datos se considera obsoleta si la eliminó una transacción que ya no está activa.</span><span class="sxs-lookup"><span data-stu-id="c320e-103">A data row is considered stale if it was deleted by a transaction that is no longer active.</span></span> <span data-ttu-id="c320e-104">Una fila obsoleta es válida para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c320e-104">A stale row is eligible for garbage collection.</span></span> <span data-ttu-id="c320e-105">A continuación se indican las características de la recolección de elementos no utilizados de [!INCLUDE[hek_2](../../includes/hek-2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c320e-105">The following are characteristics of garbage collection in [!INCLUDE[hek_2](../../includes/hek-2-md.md)]:</span></span>  
  
-   <span data-ttu-id="c320e-106">No bloqueante.</span><span class="sxs-lookup"><span data-stu-id="c320e-106">Non-blocking.</span></span> <span data-ttu-id="c320e-107">La recolección de elementos no utilizados se reparte uniformemente en el tiempo y tiene un impacto mínimo sobre la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c320e-107">Garbage collection is distributed over time with minimal impact on the workload.</span></span>  
  
-   <span data-ttu-id="c320e-108">Cooperativa.</span><span class="sxs-lookup"><span data-stu-id="c320e-108">Cooperative.</span></span> <span data-ttu-id="c320e-109">Las transacciones de usuario participan en la recolección de elementos no utilizados con el subproceso principal de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c320e-109">User transactions participate in garbage collection with main garbage-collection thread.</span></span>  
  
-   <span data-ttu-id="c320e-110">Eficiente.</span><span class="sxs-lookup"><span data-stu-id="c320e-110">Efficient.</span></span> <span data-ttu-id="c320e-111">Las transacciones de usuario desvinculan las filas obsoletas de la ruta de acceso (es decir, el índice) que se usa.</span><span class="sxs-lookup"><span data-stu-id="c320e-111">User transactions delink stale rows in the access path (the index) being used.</span></span> <span data-ttu-id="c320e-112">Esto reduce el trabajo necesario cuando se quita finalmente la fila.</span><span class="sxs-lookup"><span data-stu-id="c320e-112">This reduces the work required when the row is finally removed.</span></span>  
  
-   <span data-ttu-id="c320e-113">Responde.</span><span class="sxs-lookup"><span data-stu-id="c320e-113">Responsive.</span></span> <span data-ttu-id="c320e-114">La presión de memoria conduce a una recolección de elementos no utilizados dinámica.</span><span class="sxs-lookup"><span data-stu-id="c320e-114">Memory pressure leads to aggressive garbage collection.</span></span>  
  
-   <span data-ttu-id="c320e-115">Escalable.</span><span class="sxs-lookup"><span data-stu-id="c320e-115">Scalable.</span></span> <span data-ttu-id="c320e-116">Tras la confirmación, las transacciones de usuario hacen parte del trabajo de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c320e-116">After commit, user transactions do part of the work of garbage collection.</span></span> <span data-ttu-id="c320e-117">Cuanta más actividad transaccional hay, más transacciones desvinculan las filas obsoletas.</span><span class="sxs-lookup"><span data-stu-id="c320e-117">The more transaction activity, the more the transactions delink stale rows.</span></span>  
  
 <span data-ttu-id="c320e-118">La recolección de elementos no utilizados se controla mediante el subproceso principal de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c320e-118">Garbage collection is controlled by the main garbage collection thread.</span></span> <span data-ttu-id="c320e-119">El subproceso principal de recolección de elementos no utilizados se ejecuta cada minuto, o cuando el número de transacciones confirmadas supera un umbral interno.</span><span class="sxs-lookup"><span data-stu-id="c320e-119">The main garbage collection thread runs every minute, or when the number of committed transactions exceeds an internal threshold.</span></span> <span data-ttu-id="c320e-120">La tarea del recolector de elementos no utilizados es:</span><span class="sxs-lookup"><span data-stu-id="c320e-120">The task of the garbage collector is to:</span></span>  
  
-   <span data-ttu-id="c320e-121">Identificar las transacciones que han eliminado o actualizado un conjunto de filas y se han confirmado antes que la transacción activa más antigua.</span><span class="sxs-lookup"><span data-stu-id="c320e-121">Identify transactions that have deleted or updated a set of rows and have committed before the oldest active transaction.</span></span>  
  
-   <span data-ttu-id="c320e-122">Identificar las versiones de fila creadas por estas transacciones antiguas.</span><span class="sxs-lookup"><span data-stu-id="c320e-122">Identity row versions created by these old transactions.</span></span>  
  
-   <span data-ttu-id="c320e-123">Agrupar las filas antiguas en una o varias unidades de 16 filas cada una.</span><span class="sxs-lookup"><span data-stu-id="c320e-123">Group old rows into one or more units of 16 rows each.</span></span> <span data-ttu-id="c320e-124">Esto se hace para distribuir el trabajo del recolector de elementos no utilizados en unidades menores.</span><span class="sxs-lookup"><span data-stu-id="c320e-124">This is done to distribute the work of the garbage collector into smaller units.</span></span>  
  
-   <span data-ttu-id="c320e-125">Mover estas unidades de trabajo a la cola de recolección de elementos no utilizados, una para cada programador.</span><span class="sxs-lookup"><span data-stu-id="c320e-125">Move these work units into the garbage collection queue, one for each scheduler.</span></span> <span data-ttu-id="c320e-126">Consulte las vistas de administración dinámica del recolector de elementos no utilizados para obtener detalles: [sys.dm_xtp_gc_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xtp-gc-stats-transact-sql), [sys.dm_db_xtp_gc_cycle_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-gc-cycle-stats-transact-sql) y [sys.dm_xtp_gc_queue_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xtp-gc-queue-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c320e-126">Refer to the garbage collector DMVs for the details: [sys.dm_xtp_gc_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xtp-gc-stats-transact-sql), [sys.dm_db_xtp_gc_cycle_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-gc-cycle-stats-transact-sql), and [sys.dm_xtp_gc_queue_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xtp-gc-queue-stats-transact-sql).</span></span>  
  
 <span data-ttu-id="c320e-127">Cuando una transacción de usuario se confirma, identifica todos los elementos en cola asociados al programador en el que se ejecutó y después libera la memoria.</span><span class="sxs-lookup"><span data-stu-id="c320e-127">After a user transaction commits, it identifies all queued items associated with the scheduler it ran on and then releases the memory.</span></span> <span data-ttu-id="c320e-128">Si la cola de recolección de elementos no utilizados del programador está vacía, busca cualquier cola que no esté vacía en el nodo NUMA actual.</span><span class="sxs-lookup"><span data-stu-id="c320e-128">If the garbage collection queue on the scheduler is empty, it searches for any non-empty queue in the current NUMA node.</span></span> <span data-ttu-id="c320e-129">Si hay poca actividad transaccional y hay presión de memoria, el subproceso principal de recolector de elementos no utilizados puede acceder a las filas de cualquier cola.</span><span class="sxs-lookup"><span data-stu-id="c320e-129">If there is low transactional activity and there is memory pressure, the main garbage-collection thread can access garbage collect rows from any queue.</span></span> <span data-ttu-id="c320e-130">Si no hay ninguna actividad transaccional después de (por ejemplo) eliminar un gran número de filas y no hay presión de memoria, las filas eliminadas no se recopilarán hasta que no se reanude la actividad transaccional o hasta que haya presión de memoria.</span><span class="sxs-lookup"><span data-stu-id="c320e-130">If there is no transactional activity after (for example) deleting a large number of rows and there is no memory pressure, the deleted rows will not be garbage collected until the transactional activity resumes or there is memory pressure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c320e-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c320e-131">See Also</span></span>  
 [<span data-ttu-id="c320e-132">Administrar memoria para OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="c320e-132">Managing Memory for In-Memory OLTP</span></span>](../../database-engine/managing-memory-for-in-memory-oltp.md)  
  
  