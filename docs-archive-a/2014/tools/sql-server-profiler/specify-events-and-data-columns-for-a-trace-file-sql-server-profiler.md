---
title: Especificar eventos y columnas de datos para un archivo de seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- adding events
- traces [SQL Server], data columns
- deleting events
- removing events
- traces [SQL Server], events
ms.assetid: 7da715a3-2f03-4063-b6a4-20fd7b44e675
author: stevestein
ms.author: sstein
ms.openlocfilehash: ffb8639a187f1e7e091e382031886659bd47d7d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661732"
---
# <a name="specify-events-and-data-columns-for-a-trace-file-sql-server-profiler"></a><span data-ttu-id="7599e-102">Especificar eventos y columnas de datos para un archivo de seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="7599e-102">Specify Events and Data Columns for a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="7599e-103">En este tema se describe el modo de especificar clases de eventos y columnas de datos para seguimientos mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7599e-103">This topic describes how to specify event classes and data columns for traces by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-specify-events-and-data-columns-for-a-trace"></a><span data-ttu-id="7599e-104">Para especificar eventos y columnas de datos para un seguimiento</span><span class="sxs-lookup"><span data-stu-id="7599e-104">To specify events and data columns for a trace</span></span>  
  
1.  <span data-ttu-id="7599e-105">En el cuadro de diálogo **Propiedades de seguimiento** o **Propiedades de la plantilla de seguimiento** , haga clic en la pestaña **Selección de eventos** .</span><span class="sxs-lookup"><span data-stu-id="7599e-105">On the **Trace Properties** or **Trace Template Properties** dialog box, click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="7599e-106">La pestaña **Selección de eventos** contiene un control de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="7599e-106">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="7599e-107">El control de cuadrícula es una tabla que contiene todas las clases de eventos en las que se puede realizar un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7599e-107">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="7599e-108">La tabla contiene una fila para cada clase de evento.</span><span class="sxs-lookup"><span data-stu-id="7599e-108">The table contains one row for each event class.</span></span> <span data-ttu-id="7599e-109">Las clases de eventos pueden diferir ligeramente dependiendo del tipo y la versión del servidor al que esté conectado.</span><span class="sxs-lookup"><span data-stu-id="7599e-109">The event classes can differ slightly depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="7599e-110">Las clases de eventos se identifican en la columna **Events**de la cuadrícula y se agrupan por categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="7599e-110">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="7599e-111">En las demás columnas se enumeran las columnas de datos que pueden devolverse para cada clase de evento.</span><span class="sxs-lookup"><span data-stu-id="7599e-111">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
2.  <span data-ttu-id="7599e-112">En el cuadro de diálogo **Selección de eventos**, use el control de cuadrícula para agregar o eliminar eventos y columnas de datos del archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7599e-112">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file.</span></span>  
  
3.  <span data-ttu-id="7599e-113">Para eliminar eventos del seguimiento, desactive casilla en la columna **Eventos** para cada clase de evento.</span><span class="sxs-lookup"><span data-stu-id="7599e-113">To remove events from the trace, clear the check box in the **Events** column for each event class.</span></span>  
  
4.  <span data-ttu-id="7599e-114">Para incluir eventos en un seguimiento, active la casilla en la columna **Eventos** para cada clase de evento, o bien seleccione una columna de datos que corresponda a un evento.</span><span class="sxs-lookup"><span data-stu-id="7599e-114">To include events in a trace, check the box in the **Events** column for each event class, or check a data column that corresponds to an event.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7599e-115">Si el seguimiento se va a correlacionar con los datos del Monitor de sistema o del Monitor de rendimiento, es necesario incluir en el seguimiento las columnas de datos **Hora de inicio** y **Hora de finalización** .</span><span class="sxs-lookup"><span data-stu-id="7599e-115">If the trace is going be correlated with System Monitor or Performance Monitor data, both **Start Time** and **End Time** data columns must be included in the trace.</span></span>  
  
 <span data-ttu-id="7599e-116">Si incluye una clase de evento, todas las columnas de datos asociadas también se incluyen en el seguimiento si ha activado la casilla correspondiente a un evento.</span><span class="sxs-lookup"><span data-stu-id="7599e-116">When you include an event class, every associated data column is also included to the trace, if you have checked the box corresponding to an event.</span></span> <span data-ttu-id="7599e-117">Si ha activado la casilla de una determinada columna, solo se incluye esa columna en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7599e-117">If you checked the box for a particular column, only that column is included in the trace.</span></span>  
  
1.  <span data-ttu-id="7599e-118">Para quitar columnas de datos de una clase de eventos, desactive las casillas de la columna de datos en la fila de la clase de eventos o haga clic con el botón derecho en el encabezado de columna y seleccione la opción **Anular la selección de la columna** .</span><span class="sxs-lookup"><span data-stu-id="7599e-118">To remove data columns from an event class, clear the check boxes from the data column in the event class row, or right-click on the column header and select the **Deselect column** option.</span></span>  
  
2.  <span data-ttu-id="7599e-119">Opcionalmente, aplique filtros al seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7599e-119">Optionally, apply filters to the trace.</span></span> <span data-ttu-id="7599e-120">Para obtener más información, vea [Filtrar eventos en un seguimiento &#40;SQL Server Profiler&#41;](filter-events-in-a-trace-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="7599e-120">For more information, see [Filter Events in a Trace &#40;SQL Server Profiler&#41;](filter-events-in-a-trace-sql-server-profiler.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7599e-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7599e-121">See Also</span></span>  
 [<span data-ttu-id="7599e-122">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="7599e-122">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
