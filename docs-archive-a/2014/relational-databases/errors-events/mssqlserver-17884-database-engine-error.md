---
title: MSSQLSERVER_17884 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17884 (Database Engine error)
ms.assetid: 8d05ba05-3f71-4dc3-bd81-2ea5ac9fe843
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd5beca2a7dfd20afbf9eff196d89452ef3533d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747013"
---
# <a name="mssqlserver_17884"></a><span data-ttu-id="87e90-102">MSSQLSERVER_17884</span><span class="sxs-lookup"><span data-stu-id="87e90-102">MSSQLSERVER_17884</span></span>
    
## <a name="details"></a><span data-ttu-id="87e90-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="87e90-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87e90-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="87e90-104">Product Name</span></span>|<span data-ttu-id="87e90-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="87e90-105">SQL Server</span></span>|  
|<span data-ttu-id="87e90-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="87e90-106">Event ID</span></span>|<span data-ttu-id="87e90-107">17884</span><span class="sxs-lookup"><span data-stu-id="87e90-107">17884</span></span>|  
|<span data-ttu-id="87e90-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="87e90-108">Event Source</span></span>|<span data-ttu-id="87e90-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="87e90-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="87e90-110">Componente</span><span class="sxs-lookup"><span data-stu-id="87e90-110">Component</span></span>|<span data-ttu-id="87e90-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="87e90-111">SQLEngine</span></span>|  
|<span data-ttu-id="87e90-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="87e90-112">Symbolic Name</span></span>|<span data-ttu-id="87e90-113">SRV_SCHEDULER_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="87e90-113">SRV_SCHEDULER_DEADLOCK</span></span>|  
|<span data-ttu-id="87e90-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="87e90-114">Message Text</span></span>|<span data-ttu-id="87e90-115">Un subproceso de trabajo no ha recogido las nuevas consultas asignadas al proceso en el nodo %d durante los últimos %d segundos.</span><span class="sxs-lookup"><span data-stu-id="87e90-115">New queries assigned to process on Node %d have not been picked  up by a worker thread in the last %d seconds.</span></span> <span data-ttu-id="87e90-116">Puede que contribuya a ello la existencia de consultas de bloqueo o consultas que se ejecutan durante mucho tiempo, lo cual puede degradar el tiempo de respuesta del cliente.</span><span class="sxs-lookup"><span data-stu-id="87e90-116">Blocking or long-running queries can contribute to this condition, and may degrade client response time.</span></span> <span data-ttu-id="87e90-117">Utilice la opción de configuración "max worker threads" para aumentar el número de subprocesos permitidos u optimice las consultas que se estén ejecutando.</span><span class="sxs-lookup"><span data-stu-id="87e90-117">Use the "max worker threads" configuration option to increase number  of allowable threads, or optimize current running queries.</span></span>  <span data-ttu-id="87e90-118">Uso del proceso de SQL: %d%%.</span><span class="sxs-lookup"><span data-stu-id="87e90-118">SQL Process Utilization: %d%%.</span></span> <span data-ttu-id="87e90-119">Sistema inactivo: %d%%.</span><span class="sxs-lookup"><span data-stu-id="87e90-119">System Idle: %d%%.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="87e90-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="87e90-120">Explanation</span></span>  
 <span data-ttu-id="87e90-121">No hay ningún signo de progreso en ninguno de los programadores y esto podría deberse a interbloqueos donde ninguno de los subprocesos puede avanzar, o a que no se ha elegido ni procesado ningún trabajo nuevo.</span><span class="sxs-lookup"><span data-stu-id="87e90-121">There is no sign of progress in each of the schedulers and could be caused by deadlocks where none of the threads can advance and/or no new work can be picked up and processed.</span></span> <span data-ttu-id="87e90-122">Si la utilización del proceso es baja, otros procesos del equipo pueden estar ocasionando el colapso de la CPU del proceso de servidor.</span><span class="sxs-lookup"><span data-stu-id="87e90-122">If process utilization is low then other processes on the machine may be causing the server process CPU starvation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="87e90-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="87e90-123">User Action</span></span>  
 <span data-ttu-id="87e90-124">Determine por qué se está produciendo el bloqueo y no se observa ningún progreso, y resuelva la situación como corresponda.</span><span class="sxs-lookup"><span data-stu-id="87e90-124">Determine why there is blocking and no progress being made and resolve situation accordingly.</span></span> <span data-ttu-id="87e90-125">Si la utilización del proceso es baja, compruebe la carga del sistema ocasionada por otros procesos.</span><span class="sxs-lookup"><span data-stu-id="87e90-125">If process utilization is low check the load on the system caused by other processes.</span></span>  
  
  
