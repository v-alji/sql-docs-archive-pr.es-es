---
title: Reproducir hasta un punto de interrupción (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- breakpoints [SQL Server]
- traces [SQL Server], replaying
ms.assetid: 3caf751e-df3b-40c7-b5e8-4490ae178e0c
author: stevestein
ms.author: sstein
ms.openlocfilehash: f33b6862847b042a2613d8c2aa035dd5805493ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748408"
---
# <a name="replay-to-a-breakpoint-sql-server-profiler"></a><span data-ttu-id="13381-102">Reproducir hasta un punto de interrupción (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="13381-102">Replay to a Breakpoint (SQL Server Profiler)</span></span>
  <span data-ttu-id="13381-103">En este tema se describe cómo establecer puntos de interrupción en una tabla o archivo de seguimiento que desee reproducir mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13381-103">This topic describes how to set breakpoints in a trace file or table that you want to replay by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="13381-104">El establecimiento de puntos de interrupción en un seguimiento o archivo de seguimiento antes de comenzar la reproducción del seguimiento permite poner en pausa la reproducción del seguimiento en determinados eventos.</span><span class="sxs-lookup"><span data-stu-id="13381-104">Setting breakpoints in a trace file or table before you start to replay the trace, enables you to pause replay of the trace at specific events.</span></span> <span data-ttu-id="13381-105">El uso de puntos de interrupción durante la reproducción de un seguimiento permite usar la depuración, ya que la reproducción de scripts de seguimiento largos se puede dividir en segmentos cortos que se pueden analizar de forma incremental.</span><span class="sxs-lookup"><span data-stu-id="13381-105">Using breakpoints while replaying a trace supports debugging because you can break the replay of long trace scripts into short segments that can be analyzed incrementally.</span></span>  
  
### <a name="to-replay-to-a-breakpoint"></a><span data-ttu-id="13381-106">Para reproducir hasta un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="13381-106">To replay to a breakpoint</span></span>  
  
1.  <span data-ttu-id="13381-107">Abra el archivo o la tabla de seguimiento que desea reproducir.</span><span class="sxs-lookup"><span data-stu-id="13381-107">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="13381-108">Para obtener más información, vea [Abrir un archivo de seguimiento &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) o el Asistente para la optimización del [Abrir una tabla de seguimiento &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="13381-108">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="13381-109">Asegúrese de que el archivo o la tabla de seguimiento que abre contiene las clases de evento necesarias para la reproducción.</span><span class="sxs-lookup"><span data-stu-id="13381-109">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="13381-110">Para más información, consulte [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13381-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="13381-111">En la ventana de seguimiento, haga clic en el evento que desee utilizar como punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="13381-111">In the trace window, click an event that you want to use as a breakpoint.</span></span> <span data-ttu-id="13381-112">Para establecer un punto de interrupción, utilice uno de estos tres métodos:</span><span class="sxs-lookup"><span data-stu-id="13381-112">Use one of the following three methods to set a breakpoint:</span></span>  
  
    -   <span data-ttu-id="13381-113">Presione F9.</span><span class="sxs-lookup"><span data-stu-id="13381-113">Press F9.</span></span>  
  
    -   <span data-ttu-id="13381-114">En el menú **Reproducir** , haga clic en **Alternar punto de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="13381-114">On the **Replay** menu, click **Toggle Breakpoint**.</span></span>  
  
    -   <span data-ttu-id="13381-115">Haga clic con el botón derecho en el evento y luego haga clic en **Alternar puntos de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="13381-115">Right-click the event, and then click **Toggle Breakpoint**.</span></span>  
  
     <span data-ttu-id="13381-116">Un punto rojo aparece junto al evento de seguimiento seleccionado para indicar que se trata del punto de interrupción del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="13381-116">A red bullet appears next to the selected trace event, indicating that it is the trace breakpoint.</span></span>  
  
     <span data-ttu-id="13381-117">Repita este paso para establecer varios puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="13381-117">Repeat this step to set several breakpoints.</span></span>  
  
3.  <span data-ttu-id="13381-118">En el menú **Reproducir** , haga clic en **Iniciar**y conéctese al servidor en el que desee reproducir el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="13381-118">On the **Replay** menu, click **Start**, and connect to the server where you want to replay the trace.</span></span>  
  
4.  <span data-ttu-id="13381-119">Compruebe la configuración en el cuadro de diálogo **Configuración de reproducción** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="13381-119">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
     <span data-ttu-id="13381-120">Se inicia la reproducción, que se pone en pausa al alcanzar el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="13381-120">The replay starts, pausing when the breakpoint is reached.</span></span>  
  
5.  <span data-ttu-id="13381-121">Presione F5 para reanudar la reproducción y continuar hasta el siguiente punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="13381-121">Press F5 to resume the replay and proceed to the next breakpoint.</span></span>  
  
6.  <span data-ttu-id="13381-122">Repita el paso 5 hasta el final del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="13381-122">Repeat Step 5 through the end of the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13381-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13381-123">See Also</span></span>  
 <span data-ttu-id="13381-124">[Reproducir hasta un cursor &#40;SQL Server Profiler&#41;](replay-to-a-cursor-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="13381-124">[Replay to a Cursor &#40;SQL Server Profiler&#41;](replay-to-a-cursor-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="13381-125">[Reproducir seguimientos](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="13381-125">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="13381-126">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="13381-126">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
