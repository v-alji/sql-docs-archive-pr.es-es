---
title: Reproducir hasta un cursor (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- replaying cursors
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 89eadc41-4424-4a1c-ba61-0b52c851cdb1
author: stevestein
ms.author: sstein
ms.openlocfilehash: bfc5ba06b60100bf8ecc8d04909371021a5b00e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748407"
---
# <a name="replay-to-a-cursor-sql-server-profiler"></a><span data-ttu-id="a1193-102">Reproducir hasta un cursor (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="a1193-102">Replay to a Cursor (SQL Server Profiler)</span></span>
  <span data-ttu-id="a1193-103">En este tema se describe cómo reproducir archivos o tablas de seguimiento que se ponen en pausa al alcanzar un cursor mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1193-103">This topic describes how to replay trace files or tables that pause when a cursor is reached by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="a1193-104">La pausa de seguimientos en cursores es compatible con la depuración porque la reproducción de scripts de seguimiento largos se puede dividir en segmentos cortos que se pueden analizar de forma incremental.</span><span class="sxs-lookup"><span data-stu-id="a1193-104">Pausing traces at cursors supports debugging because you can break the replay of long trace scripts into short segments that can be analyzed incrementally.</span></span>  
  
### <a name="to-replay-to-the-cursor"></a><span data-ttu-id="a1193-105">Para reproducir hasta el cursor</span><span class="sxs-lookup"><span data-stu-id="a1193-105">To replay to the cursor</span></span>  
  
1.  <span data-ttu-id="a1193-106">Abra el archivo o la tabla de seguimiento que desea reproducir.</span><span class="sxs-lookup"><span data-stu-id="a1193-106">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="a1193-107">Para obtener más información, vea [Abrir un archivo de seguimiento &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) o el Asistente para la optimización del [Abrir una tabla de seguimiento &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="a1193-107">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="a1193-108">Asegúrese de que el archivo o la tabla de seguimiento que abre contiene las clases de evento necesarias para la reproducción.</span><span class="sxs-lookup"><span data-stu-id="a1193-108">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="a1193-109">Para más información, consulte [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1193-109">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="a1193-110">En la ventana de seguimiento, haga clic en un evento.</span><span class="sxs-lookup"><span data-stu-id="a1193-110">In the trace window, click an event.</span></span>  
  
3.  <span data-ttu-id="a1193-111">En el menú **Reproducir** , haga clic en **Ejecutar hasta el cursor**y, a continuación, conéctese al servidor en el que desea reproducir el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a1193-111">On the **Replay** menu, click **Run to Cursor**, and then connect to the server where you want to replay the trace.</span></span>  
  
4.  <span data-ttu-id="a1193-112">Compruebe la configuración en el cuadro de diálogo **Configuración de reproducción** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1193-112">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a1193-113">Se inicia la reproducción, que se pone en pausa al alcanzar el primer cursor.</span><span class="sxs-lookup"><span data-stu-id="a1193-113">The replay starts, pausing when the first cursor is reached.</span></span>  
  
5.  <span data-ttu-id="a1193-114">Presione F5 para reanudar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a1193-114">Press F5 to resume the trace.</span></span>  
  
6.  <span data-ttu-id="a1193-115">Repita el paso 5 hasta el final del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a1193-115">Repeat Step 5 through the end of the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1193-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1193-116">See Also</span></span>  
 <span data-ttu-id="a1193-117">[Reproducir hasta un punto de interrupción &#40;SQL Server Profiler&#41;](replay-to-a-breakpoint-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="a1193-117">[Replay to a Breakpoint &#40;SQL Server Profiler&#41;](replay-to-a-breakpoint-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="a1193-118">[Reproducir seguimientos](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="a1193-118">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="a1193-119">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="a1193-119">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
