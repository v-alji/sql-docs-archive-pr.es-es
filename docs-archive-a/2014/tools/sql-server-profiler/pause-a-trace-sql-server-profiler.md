---
title: Pausar un seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- pausing traces
- temporarily stopping traces
- traces [SQL Server], pausing
- stopping traces
ms.assetid: 432b9b0c-b5e7-47f3-a71b-310fb3bf2445
author: stevestein
ms.author: sstein
ms.openlocfilehash: cdc9dbbd01099b1d33787a72b0bd59b65cea722e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743742"
---
# <a name="pause-a-trace-sql-server-profiler"></a><span data-ttu-id="f29ab-102">Pausar un seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="f29ab-102">Pause a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="f29ab-103">La pausa de un seguimiento impide la captura de más datos de eventos hasta que se vuelva a iniciar.</span><span class="sxs-lookup"><span data-stu-id="f29ab-103">Pausing a trace prevents further event data from being captured until the trace is restarted.</span></span>  
  
 <span data-ttu-id="f29ab-104">La pausa de un seguimiento impide la captura de datos de eventos hasta que se vuelve a iniciar.</span><span class="sxs-lookup"><span data-stu-id="f29ab-104">When you pause a trace, you prevent event data from being captured until the trace is restarted.</span></span> <span data-ttu-id="f29ab-105">Al iniciarlo de nuevo se reanudan las operaciones de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f29ab-105">Restarting a trace lets trace operations resume.</span></span> <span data-ttu-id="f29ab-106">Tras reiniciar una traza, no se pierden los datos capturados previamente.</span><span class="sxs-lookup"><span data-stu-id="f29ab-106">No previously captured data is lost after a restart.</span></span> <span data-ttu-id="f29ab-107">Cuando se vuelve a iniciar el seguimiento, se reanuda la captura de datos a partir de ese punto.</span><span class="sxs-lookup"><span data-stu-id="f29ab-107">When the trace is restarted, data capturing resumes from that point onward.</span></span> <span data-ttu-id="f29ab-108">Cuando un seguimiento está pausado, puede cambiar el nombre, los eventos, las columnas y los filtros.</span><span class="sxs-lookup"><span data-stu-id="f29ab-108">While a trace is paused, you can change the name, events, columns, and filters.</span></span> <span data-ttu-id="f29ab-109">Sin embargo, no puede cambiar los destinos a los que envía los datos del seguimiento ni la conexión del servidor.</span><span class="sxs-lookup"><span data-stu-id="f29ab-109">However, you cannot change the destinations to which you are sending the trace data, nor change the server connection.</span></span>  
  
### <a name="to-pause-a-trace"></a><span data-ttu-id="f29ab-110">Para pausar un seguimiento</span><span class="sxs-lookup"><span data-stu-id="f29ab-110">To pause a trace</span></span>  
  
1.  <span data-ttu-id="f29ab-111">Seleccione una ventana que contenga un seguimiento que se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="f29ab-111">Select a window that contains a running trace.</span></span>  
  
2.  <span data-ttu-id="f29ab-112">En el menú **Archivo** , haga clic en **Pausar seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="f29ab-112">On the **File** menu, click **Pause Trace**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f29ab-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f29ab-113">See Also</span></span>  
 [<span data-ttu-id="f29ab-114">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f29ab-114">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
