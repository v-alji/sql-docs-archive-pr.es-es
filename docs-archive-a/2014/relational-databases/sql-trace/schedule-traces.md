---
title: Programar seguimientos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], events
- traces [SQL Server]
- traces [SQL Server], stopping
- events [SQL Server], filters
- scheduling traces [SQL Server]
- traces [SQL Server], scheduling
- stopping traces
ms.assetid: 620b79db-924b-4502-8af3-39efcfca245d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a698d88db35c84f7611293cf45807203c883865a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674754"
---
# <a name="schedule-traces"></a><span data-ttu-id="1ae76-102">Programar seguimientos</span><span class="sxs-lookup"><span data-stu-id="1ae76-102">Schedule Traces</span></span>
  <span data-ttu-id="1ae76-103">En Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]hay dos formas de programar trazas.</span><span class="sxs-lookup"><span data-stu-id="1ae76-103">There are two ways to schedule tracing in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1ae76-104">Puede:</span><span class="sxs-lookup"><span data-stu-id="1ae76-104">You can:</span></span>  
  
-   <span data-ttu-id="1ae76-105">Habilitar una hora de detención de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1ae76-105">Enable a trace stop time.</span></span>  
  
-   <span data-ttu-id="1ae76-106">Utilizar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para programar una seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1ae76-106">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to schedule a trace.</span></span>  
  
## <a name="specifying-a-stop-time"></a><span data-ttu-id="1ae76-107">Especificar una hora de detención</span><span class="sxs-lookup"><span data-stu-id="1ae76-107">Specifying a Stop Time</span></span>  
 <span data-ttu-id="1ae76-108">Puede especificar una hora de detención de seguimiento si utiliza procedimientos almacenados de [!INCLUDE[tsql](../../includes/tsql-md.md)] o si utiliza el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ae76-108">You can specify a trace stop time if you use [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures or if you use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="1ae76-109">La hora de detención debe establecerse al configurar originalmente la seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1ae76-109">The stop time must be set when the trace is originally configured.</span></span>  
  
## <a name="scheduling-traces-by-using-sql-server-agent"></a><span data-ttu-id="1ae76-110">Programar seguimientos mediante el Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ae76-110">Scheduling Traces by Using SQL Server Agent</span></span>  
 <span data-ttu-id="1ae76-111">La mejor forma de programar seguimientos consiste en usar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para iniciar el seguimiento y, después, especificar una hora de detención de seguimiento mediante el procedimiento almacenado de [!INCLUDE[tsql](../../includes/tsql-md.md)]**sp_trace_setstatus**o el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ae76-111">The best way to schedule traces is to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to start the trace and then specify a trace stop time by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure **sp_trace_setstatus**, or [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
 <span data-ttu-id="1ae76-112">**Para establecer un filtro de hora de finalización para una seguimiento**</span><span class="sxs-lookup"><span data-stu-id="1ae76-112">**To set an end time filter for a trace**</span></span>  
  
 [<span data-ttu-id="1ae76-113">Filtrar eventos basándose en la hora de finalización del evento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="1ae76-113">Filter Events Based on the Event End Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-end-time-sql-server-profiler.md)  
  
 [<span data-ttu-id="1ae76-114">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1ae76-114">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="1ae76-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ae76-115">See Also</span></span>  
 [<span data-ttu-id="1ae76-116">Tareas administrativas automatizadas &#40;Agente SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1ae76-116">Automated Administration Tasks &#40;SQL Server Agent&#41;</span></span>](../../ssms/agent/sql-server-agent.md)  
  
  
