---
title: Iniciar un seguimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, stopping traces
- pausing traces
- Profiler [SQL Server Profiler], stopping traces
- Profiler [SQL Server Profiler], starting traces
- traces [SQL Server], starting
- SQL Server Profiler, pausing traces
- traces [SQL Server], stopping
- Profiler [SQL Server Profiler], pausing traces
- traces [SQL Server], pausing
- SQL Server Profiler, starting traces
- stopping traces
- starting traces
ms.assetid: aeeb38eb-229a-4c8b-ad66-57e9ce45fb6a
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2b75519631269a1213077a4e295ac73fca1b950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747333"
---
# <a name="start-a-trace"></a><span data-ttu-id="e25a9-102">Iniciar un seguimiento</span><span class="sxs-lookup"><span data-stu-id="e25a9-102">Start a Trace</span></span>
  <span data-ttu-id="e25a9-103">Una vez definida un nuevo seguimiento o creada una plantilla mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], puede iniciar, pausar o detener la captura de datos con la nueva definición de seguimiento o plantilla.</span><span class="sxs-lookup"><span data-stu-id="e25a9-103">After you have defined a new trace or created a template by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can start, pause, or stop capturing data by using the new trace definition or template.</span></span>  
  
## <a name="starting-a-trace"></a><span data-ttu-id="e25a9-104">Iniciar un seguimiento</span><span class="sxs-lookup"><span data-stu-id="e25a9-104">Starting a Trace</span></span>  
 <span data-ttu-id="e25a9-105">Si inicia un seguimiento y el origen definido es una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crea una cola para colocar temporalmente los eventos de servidor capturados.</span><span class="sxs-lookup"><span data-stu-id="e25a9-105">When you start a trace and the defined source is an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates a queue that provides a temporary holding place for captured server events.</span></span>  
  
 <span data-ttu-id="e25a9-106">Si utiliza el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para tener acceso a Seguimiento de SQL, al iniciar un seguimiento se abre una nueva ventana de seguimiento (si aún no hay ninguna abierta) y los datos se capturan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="e25a9-106">When you use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to access SQL Trace, a new trace window opens (if one is not already open) when a trace is started, and data is immediately captured.</span></span>  
  
 <span data-ttu-id="e25a9-107">Si se utilizan los procedimientos almacenados del sistema [!INCLUDE[tsql](../../includes/tsql-md.md)] para tener acceso a Seguimiento de SQL, debe iniciar un seguimiento cada vez que se inicie una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que los datos se capturen.</span><span class="sxs-lookup"><span data-stu-id="e25a9-107">When you use [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to access SQL Trace, you must start a trace every time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts for data to be captured.</span></span> <span data-ttu-id="e25a9-108">Una vez iniciado el seguimiento, solo puede modificar el nombre de este.</span><span class="sxs-lookup"><span data-stu-id="e25a9-108">When a trace has been started, you can modify only the name of the trace.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e25a9-109">Si trabaja con seguimientos existentes, puede ver las propiedades, pero no modificarlas.</span><span class="sxs-lookup"><span data-stu-id="e25a9-109">When working with existing traces, you can view the properties, but you cannot modify the properties.</span></span> <span data-ttu-id="e25a9-110">Para modificar las propiedades, detenga o pause el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e25a9-110">To modify the properties, stop or pause the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e25a9-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e25a9-111">See Also</span></span>  
 <span data-ttu-id="e25a9-112">[Iniciar un seguimiento automáticamente después de conectarse a un servidor &#40;SQL Server Profiler&#41;](start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="e25a9-112">[Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;](start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="e25a9-113">[Pausar un SQL Server Profiler de &#40;de seguimiento&#41;](pause-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="e25a9-113">[Pause a Trace &#40;SQL Server Profiler&#41;](pause-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="e25a9-114">[Detener un SQL Server Profiler de &#40;de seguimiento&#41;](stop-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="e25a9-114">[Stop a Trace &#40;SQL Server Profiler&#41;](stop-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="e25a9-115">[Borrar una ventana de seguimiento &#40;SQL Server Profiler&#41;](clear-a-trace-window-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="e25a9-115">[Clear a Trace Window &#40;SQL Server Profiler&#41;](clear-a-trace-window-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="e25a9-116">Ejecutar un seguimiento después de haberlo pausado o detenido &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="e25a9-116">Run a Trace After It Has Been Paused or Stopped &#40;SQL Server Profiler&#41;</span></span>](run-a-trace-after-it-has-been-paused-or-stopped-sql-server-profiler.md)  
  
  
