---
title: Reproducir seguimientos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, replaying traces
- Run to Cursor option
- Toggle Breakpoint option
- traces [SQL Server], replaying
- replaying traces
- playback engine [SQL Server Profiler]
- events [SQL Server], replaying traces
- Profiler [SQL Server Profiler], replaying traces
ms.assetid: da958d3c-7f3e-44c9-aecc-8a9493bea7c0
author: stevestein
ms.author: sstein
ms.openlocfilehash: c485317d1343958f9c430b73d858130097d44d75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748406"
---
# <a name="replay-traces"></a><span data-ttu-id="f2a26-102">Reproducir seguimientos</span><span class="sxs-lookup"><span data-stu-id="f2a26-102">Replay Traces</span></span>
  <span data-ttu-id="f2a26-103">La reproducción es la capacidad de reproducir la actividad capturada en un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f2a26-103">Replay is the ability to reproduce activity that has been captured in a trace.</span></span> <span data-ttu-id="f2a26-104">Al crear o modificar un seguimiento, puede guardarlo para reproducirlo posteriormente.</span><span class="sxs-lookup"><span data-stu-id="f2a26-104">When you create or edit a trace, you can save the trace to a file and replay it later.</span></span> <span data-ttu-id="f2a26-105">Puede utilizar [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para reproducir la actividad de seguimiento de un equipo único.</span><span class="sxs-lookup"><span data-stu-id="f2a26-105">You can use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to replay trace activity from a single computer.</span></span> <span data-ttu-id="f2a26-106">Para las cargas de trabajo grandes, emplee la utilidad Distributed Replay para reproducir la información de seguimiento de varios equipos.</span><span class="sxs-lookup"><span data-stu-id="f2a26-106">For large workloads, use the Distributed Replay Utility to replay trace data from multiple computers.</span></span>  
  
 <span data-ttu-id="f2a26-107">En esta sección se describe cómo utilizar las características de reproducción de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2a26-107">This section describes how to use the replay features of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="f2a26-108">Para obtener más información sobre la utilidad Distributed Replay, vea [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="f2a26-108">For more information about the Distributed Replay Utility, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="f2a26-109">incluye un motor de reproducción de varios subprocesos que puede simular conexiones de usuario y la Autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2a26-109">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="f2a26-110">La reproducción es útil para solucionar problemas de aplicaciones o procesos.</span><span class="sxs-lookup"><span data-stu-id="f2a26-110">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="f2a26-111">Cuando haya identificado el problema e implementado las acciones para corregirlo, ejecute el seguimiento que encontró el posible problema en la aplicación o proceso corregido.</span><span class="sxs-lookup"><span data-stu-id="f2a26-111">When you have identified the problem and implemented corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="f2a26-112">A continuación, reproduzca el seguimiento original y compare los resultados.</span><span class="sxs-lookup"><span data-stu-id="f2a26-112">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="f2a26-113">La reproducción de seguimientos admite la depuración por medio de las opciones **Alternar punto de interrupción** y **Ejecutar hasta el cursor** del menú **Reproducir** de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2a26-113">Trace replay supports debugging by using the **Toggle Breakpoint** and the **Run to Cursor** options on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Replay** menu.</span></span> <span data-ttu-id="f2a26-114">Estas opciones ofrecen mejoras especialmente en el análisis de scripts largos, ya que pueden dividir la reproducción del seguimiento en segmentos más cortos para analizarlos de forma incremental.</span><span class="sxs-lookup"><span data-stu-id="f2a26-114">These options especially improve the analysis of long scripts because they can break the replay of the trace into short segments so they can be analyzed incrementally.</span></span>  
  
 <span data-ttu-id="f2a26-115">Para obtener más información sobre los permisos necesarios para reproducir un seguimiento, vea [Permisos necesarios para ejecutar SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="f2a26-115">For information about the permissions required to replay traces, see [Permissions Required to Run SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f2a26-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f2a26-116">In This Section</span></span>  
  
|<span data-ttu-id="f2a26-117">Tema</span><span class="sxs-lookup"><span data-stu-id="f2a26-117">Topic</span></span>|<span data-ttu-id="f2a26-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2a26-118">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f2a26-119">Requisitos de reproducción</span><span class="sxs-lookup"><span data-stu-id="f2a26-119">Replay Requirements</span></span>](replay-requirements.md)|<span data-ttu-id="f2a26-120">Describe los eventos que se deben incluir en una definición de seguimiento para reproducirla con [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2a26-120">Describes the events that must be included in a trace definition so that it can be replayed with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="f2a26-121">Opciones de reproducción &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="f2a26-121">Replay Options &#40;SQL Server Profiler&#41;</span></span>](replay-options-sql-server-profiler.md)|<span data-ttu-id="f2a26-122">Describe las opciones del cuadro de diálogo **Configuración de reproducción** del [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2a26-122">Describes the options you can set in the **Replay Configuration** dialog box of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="f2a26-123">Consideraciones para reproducir seguimientos &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="f2a26-123">Considerations for Replaying Traces &#40;SQL Server Profiler&#41;</span></span>](considerations-for-replaying-traces-sql-server-profiler.md)|<span data-ttu-id="f2a26-124">Describe los eventos de seguimiento que no se pueden reproducir con [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] y los efectos de reproducir seguimientos en el rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="f2a26-124">Describes trace events that can not be replayed with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and the effects on server performance of replaying traces.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2a26-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2a26-125">See Also</span></span>  
 [<span data-ttu-id="f2a26-126">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="f2a26-126">SQL Server Distributed Replay</span></span>](../distributed-replay/sql-server-distributed-replay.md)  
  
  
