---
title: Configuración de SQL Server Profiler-reproducción (opciones avanzadas de reproducción) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.generaloptions.advanced.f1
helpviewer_keywords:
- Replay Configuration dialog box
ms.assetid: b4eb34f7-3af6-4a44-ba7e-2b8430ec3cd7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 95070d8defb5b7778859ce470aaa8cfc85955ba6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748227"
---
# <a name="sql-server-profiler---replay-configuration-advanced-replay-options"></a><span data-ttu-id="d766e-102">SQL Server Profiler (Configuración de reproducción/página Opciones avanzadas de reproducción)</span><span class="sxs-lookup"><span data-stu-id="d766e-102">SQL Server Profiler - Replay Configuration (Advanced Replay Options)</span></span>
  <span data-ttu-id="d766e-103">En el cuadro de diálogo **Configuración de reproducción** , utilice la pestaña **Opciones avanzadas de reproducción** para especificar cómo reproducir un archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d766e-103">In the **Replay Configuration** dialog box, use the **Advanced Replay Options** tab to specify how to replay a trace file.</span></span>  
  
 <span data-ttu-id="d766e-104">Para ver esta ventana, utilice el [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] para abrir un seguimiento o un archivo de seguimiento que contenga los eventos adecuados para la reproducción.</span><span class="sxs-lookup"><span data-stu-id="d766e-104">To view this window, use [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to open a trace file or table that contains the appropriate events for replay.</span></span> <span data-ttu-id="d766e-105">Para más información, consulte [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d766e-105">For more information, see [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span></span> <span data-ttu-id="d766e-106">Cuando el archivo o tabla de seguimiento esté abierto, en el menú **Reproducir** , haga clic en **Iniciar**, establezca la conexión con la sesión de SQL Server donde desea reproducir el seguimiento y haga clic en la pestaña **Opciones avanzadas de reproducción** .</span><span class="sxs-lookup"><span data-stu-id="d766e-106">While the trace file or table is open, on the **Replay** menu, click **Start**, connect to the instance of SQL Server where you want to replay the trace, and then click the **Advanced Replay Options** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d766e-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="d766e-107">Options</span></span>  
 <span data-ttu-id="d766e-108">**Reproducir los SPID del sistema**</span><span class="sxs-lookup"><span data-stu-id="d766e-108">**Replay system SPIDs**</span></span>  
 <span data-ttu-id="d766e-109">Especifica si el [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] reproduce identificadores de proceso del sistema (SPID).</span><span class="sxs-lookup"><span data-stu-id="d766e-109">Specifies whether [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] replays system process identifiers (SPIDs).</span></span>  
  
 <span data-ttu-id="d766e-110">**Reproducir solo un SPID**</span><span class="sxs-lookup"><span data-stu-id="d766e-110">**Replay one SPID only**</span></span>  
 <span data-ttu-id="d766e-111">Solo reproduce la actividad del archivo de seguimiento de origen relacionada con el SPID seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d766e-111">Replays only the activity in the source trace file that is related to the selected SPID.</span></span>  
  
 <span data-ttu-id="d766e-112">**SPID para reproducir**</span><span class="sxs-lookup"><span data-stu-id="d766e-112">**SPID to replay**</span></span>  
 <span data-ttu-id="d766e-113">Especifique el SPID que desea reproducir.</span><span class="sxs-lookup"><span data-stu-id="d766e-113">Specify which SPID to replay.</span></span>  
  
 <span data-ttu-id="d766e-114">**Limitar reproducción por fecha y hora**</span><span class="sxs-lookup"><span data-stu-id="d766e-114">**Limit replay by date and time**</span></span>  
 <span data-ttu-id="d766e-115">Active esta opción para reproducir solo una parte del archivo de seguimiento de origen.</span><span class="sxs-lookup"><span data-stu-id="d766e-115">Check to replay only a portion of the source trace file.</span></span>  
  
 <span data-ttu-id="d766e-116">**Hora de inicio**</span><span class="sxs-lookup"><span data-stu-id="d766e-116">**Start time**</span></span>  
 <span data-ttu-id="d766e-117">Fecha y hora en que debe comenzar la reproducción del archivo de seguimiento de origen.</span><span class="sxs-lookup"><span data-stu-id="d766e-117">Date and time in the source trace file where the replay should start.</span></span>  
  
 <span data-ttu-id="d766e-118">**Hora de finalización**</span><span class="sxs-lookup"><span data-stu-id="d766e-118">**End time**</span></span>  
 <span data-ttu-id="d766e-119">Fecha y hora en que debe detenerse la reproducción del archivo de seguimiento de origen.</span><span class="sxs-lookup"><span data-stu-id="d766e-119">Date and time in the source trace file where the replay should stop.</span></span>  
  
 <span data-ttu-id="d766e-120">**Intervalo de espera del monitor de estado (seg.)**</span><span class="sxs-lookup"><span data-stu-id="d766e-120">**Health monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="d766e-121">Especifique el intervalo de espera de la reproducción en segundos.</span><span class="sxs-lookup"><span data-stu-id="d766e-121">Specify the wait interval to replay in seconds.</span></span> <span data-ttu-id="d766e-122">El valor predeterminado es 3600 segundos (1 hora).</span><span class="sxs-lookup"><span data-stu-id="d766e-122">Default is 3600 seconds (1 hour).</span></span> <span data-ttu-id="d766e-123">Esta configuración afecta al tiempo que puede ejecutarse un proceso antes de que lo finalice el monitor de estado.</span><span class="sxs-lookup"><span data-stu-id="d766e-123">This setting affects the amount of time a process is allowed to run before being terminated by the health monitor.</span></span>  
  
 <span data-ttu-id="d766e-124">**Intervalo de sondeo del monitor de estado (seg.)**</span><span class="sxs-lookup"><span data-stu-id="d766e-124">**Health monitor poll interval (sec)**</span></span>  
 <span data-ttu-id="d766e-125">Especifique el intervalo de sondeo del monitor de estado durante la reproducción en segundos.</span><span class="sxs-lookup"><span data-stu-id="d766e-125">Specify the health monitor poll interval during replay in seconds.</span></span> <span data-ttu-id="d766e-126">El valor predeterminado es 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="d766e-126">Default is 60 seconds.</span></span> <span data-ttu-id="d766e-127">Este valor permite al usuario configurar la frecuencia con que el monitor de estado sondea los candidatos para terminar.</span><span class="sxs-lookup"><span data-stu-id="d766e-127">This value allows the user to configure how often the health monitor polls for candidates for termination.</span></span>  
  
 <span data-ttu-id="d766e-128">**Habilitar monitor de procesos bloqueados de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="d766e-128">**Enable SQL Server blocked processes monitor**</span></span>  
 <span data-ttu-id="d766e-129">Habilita un proceso que busca procesos bloqueados o de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d766e-129">Enables a process that searches for blocked or blocking processes.</span></span>  
  
 <span data-ttu-id="d766e-130">**Intervalo de espera del monitor de procesos bloqueados (seg.)**</span><span class="sxs-lookup"><span data-stu-id="d766e-130">**Blocked processes monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="d766e-131">Configura la frecuencia con que el monitor de procesos bloqueados busca procesos bloqueados o de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d766e-131">Configures how often the blocked processes monitor searches for blocked or blocking processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d766e-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d766e-132">See Also</span></span>  
 <span data-ttu-id="d766e-133">[Reproducir una tabla de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="d766e-133">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="d766e-134">[Reproducir un archivo de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="d766e-134">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="d766e-135">Reproducir seguimientos</span><span class="sxs-lookup"><span data-stu-id="d766e-135">Replay Traces</span></span>](../tools/sql-server-profiler/replay-traces.md)  
  
  
