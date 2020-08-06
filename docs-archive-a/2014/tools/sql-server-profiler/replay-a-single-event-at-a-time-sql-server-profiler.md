---
title: Reproducir un único evento cada vez (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- events [SQL Server], replaying single event at a time
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 220fb192-9636-41a2-b15c-62af6cab8fff
author: stevestein
ms.author: sstein
ms.openlocfilehash: 457bc94d9d8eae470fb60b450d30441c07e676df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748417"
---
# <a name="replay-a-single-event-at-a-time-sql-server-profiler"></a><span data-ttu-id="6c084-102">Reproducir un único evento cada vez (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="6c084-102">Replay a Single Event at a Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="6c084-103">En este tema se describe cómo reproducir un solo evento cada vez en un archivo o tabla de reproducción de seguimientos mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c084-103">This topic describes how to replay one event at a time in a replay trace file or table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-replay-a-single-event-at-a-time"></a><span data-ttu-id="6c084-104">Para reproducir un solo evento cada vez</span><span class="sxs-lookup"><span data-stu-id="6c084-104">To replay a single event at a time</span></span>  
  
1.  <span data-ttu-id="6c084-105">Abra el archivo o la tabla de seguimiento que desea reproducir.</span><span class="sxs-lookup"><span data-stu-id="6c084-105">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="6c084-106">Para obtener más información, vea [Abrir un archivo de seguimiento &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) o el Asistente para la optimización del [Abrir una tabla de seguimiento &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="6c084-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="6c084-107">Asegúrese de que el archivo o la tabla de seguimiento que abre contiene las clases de evento necesarias para la reproducción.</span><span class="sxs-lookup"><span data-stu-id="6c084-107">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="6c084-108">Para más información, consulte [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c084-108">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="6c084-109">En el menú **Reproducir** , haga clic en **Paso**y conéctese a la instancia de servidor en el que desea reproducir el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6c084-109">On the **Replay** menu, click **Step**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="6c084-110">Compruebe la configuración en el cuadro de diálogo **Configuración de reproducción** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6c084-110">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span> <span data-ttu-id="6c084-111">Para obtener más información sobre cómo especificar la configuración en el cuadro de diálogo **Configuración de reproducción**, vea [Reproducir un archivo de seguimiento &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) o [Reproducir una tabla de seguimiento &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="6c084-111">For more information about specifying settings on the **Replay Configuration** dialog box, see [Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) or [Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md).</span></span>  
  
4.  <span data-ttu-id="6c084-112">Para reproducir el primer evento, haga clic en **Aceptar** en el cuadro de diálogo **Configuración de reproducción** .</span><span class="sxs-lookup"><span data-stu-id="6c084-112">To replay the first event, click **OK** in the **Replay Configuration** dialog box.</span></span>  
  
5.  <span data-ttu-id="6c084-113">Para reproducir eventos posteriores, en el menú **Reproducir** , haga clic en **Paso**o pulse F10.</span><span class="sxs-lookup"><span data-stu-id="6c084-113">To replay subsequent events, on the **Replay** menu, click **Step**, or press F10.</span></span> <span data-ttu-id="6c084-114">Vuelva a hacer clic en **Paso** o pulse F10 para cada evento.</span><span class="sxs-lookup"><span data-stu-id="6c084-114">Repeat clicking **Step** or pressing F10 for each event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c084-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c084-115">See Also</span></span>  
 <span data-ttu-id="6c084-116">[Reproducir seguimientos](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="6c084-116">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="6c084-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="6c084-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
