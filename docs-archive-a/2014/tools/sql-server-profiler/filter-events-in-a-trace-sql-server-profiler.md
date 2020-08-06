---
title: Filtrar eventos en un seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: 0fd63573-3b35-4f67-9e1e-ed9aabee11a8
author: stevestein
ms.author: sstein
ms.openlocfilehash: fef9dd6956d407011261c54f796a751a0bf94941
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749006"
---
# <a name="filter-events-in-a-trace-sql-server-profiler"></a><span data-ttu-id="22586-102">Filtrar eventos en un seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="22586-102">Filter Events in a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="22586-103">Los filtros limitan los eventos que se recopilan en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22586-103">Filters limit the events collected in a trace.</span></span> <span data-ttu-id="22586-104">Si no se establece un filtro, se devolverán todos los eventos de las clases de eventos seleccionadas en el resultado del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22586-104">If a filter is not set, all events of the selected event classes are returned in the trace output.</span></span> <span data-ttu-id="22586-105">No es obligatorio establecer un filtro para un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22586-105">It is not mandatory to set a filter for a trace.</span></span> <span data-ttu-id="22586-106">Sin embargo, un filtro minimiza la sobrecarga que comporta una traza.</span><span class="sxs-lookup"><span data-stu-id="22586-106">However, a filter minimizes the overhead that is incurred during tracing.</span></span>  
  
 <span data-ttu-id="22586-107">Para agregar filtros a las definiciones de seguimiento, utilice la pestaña **Selección de eventos** del cuadro de diálogo **Propiedades de seguimiento** o **Propiedades de la plantilla de seguimiento** .</span><span class="sxs-lookup"><span data-stu-id="22586-107">You add filters to trace definitions by using the **Events Selection** tab of the **Trace Properties** or **Trace Template Properties** dialog box.</span></span>  
  
### <a name="to-filter-events-in-a-trace"></a><span data-ttu-id="22586-108">Para filtrar los eventos de un seguimiento</span><span class="sxs-lookup"><span data-stu-id="22586-108">To filter events in a trace</span></span>  
  
1.  <span data-ttu-id="22586-109">En el cuadro de diálogo **Propiedades de seguimiento** o **Propiedades de la plantilla de seguimiento** , haga clic en la pestaña **Selección de eventos** .</span><span class="sxs-lookup"><span data-stu-id="22586-109">In the **Trace Properties** or **Trace Template Properties** dialog box, click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="22586-110">La pestaña **Selección de eventos** contiene un control de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="22586-110">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="22586-111">El control de cuadrícula es una tabla que contiene todas las clases de eventos en las que se puede realizar un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22586-111">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="22586-112">La tabla contiene una fila para cada clase de evento.</span><span class="sxs-lookup"><span data-stu-id="22586-112">The table contains one row for each event class.</span></span> <span data-ttu-id="22586-113">Las clases de eventos pueden diferir ligeramente dependiendo del tipo y la versión del servidor al que esté conectado.</span><span class="sxs-lookup"><span data-stu-id="22586-113">The event classes may differ slightly, depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="22586-114">Las clases de eventos se identifican en la columna **Events**de la cuadrícula y se agrupan por categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="22586-114">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="22586-115">En las demás columnas se enumeran las columnas de datos que pueden devolverse para cada clase de evento.</span><span class="sxs-lookup"><span data-stu-id="22586-115">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
2.  <span data-ttu-id="22586-116">Haga clic en **Filtros de columna.**</span><span class="sxs-lookup"><span data-stu-id="22586-116">Click **Column Filters.**</span></span>  
  
     <span data-ttu-id="22586-117">La pestaña **Editar filtro**.</span><span class="sxs-lookup"><span data-stu-id="22586-117">The **Edit Filter**dialog box appears.</span></span> <span data-ttu-id="22586-118">La pestaña **Editar filtro**incluye una lista de operadores de comparación que se pueden utilizar para filtrar los eventos en un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22586-118">The **Edit Filter**dialog box contains a list of comparison operators that you can use to filter events in a trace.</span></span>  
  
3.  <span data-ttu-id="22586-119">Para aplicar un filtro, haga clic en el operador de comparación y escriba un valor para utilizarlo con el filtro.</span><span class="sxs-lookup"><span data-stu-id="22586-119">To apply a filter, click the comparison operator, and type a value to use for the filter.</span></span>  
  
4.  <span data-ttu-id="22586-120">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="22586-120">Click **OK**.</span></span>  
  
 <span data-ttu-id="22586-121">**Consideraciones:**</span><span class="sxs-lookup"><span data-stu-id="22586-121">**Considerations:**</span></span>  
  
-   <span data-ttu-id="22586-122">Si establece condiciones de filtro en las columnas de datos **StartTime** y **EndTime** de la pestaña Selección de eventos, asegúrese de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22586-122">If you set filter conditions on the **StartTime** and **EndTime** data columns of the Events Selection tab, then make sure that:</span></span>  
  
    -   <span data-ttu-id="22586-123">La fecha especificada tiene el formato `YYYY/MM/DD HH:mm:sec`.</span><span class="sxs-lookup"><span data-stu-id="22586-123">The date you enter matches this format: `YYYY/MM/DD HH:mm:sec`.</span></span>  
  
         <span data-ttu-id="22586-124">O</span><span class="sxs-lookup"><span data-stu-id="22586-124">-OR-</span></span>  
  
    -   <span data-ttu-id="22586-125">Se ha seleccionado la opción**Usar la configuración regional para mostrar valores de fecha y hora** del cuadro de diálogo **Opciones generales** .</span><span class="sxs-lookup"><span data-stu-id="22586-125">**Use regional settings to display date and time values** is checked in the **General Options** dialog box.</span></span> <span data-ttu-id="22586-126">Para ver el cuadro de diálogo **Opciones generales**, en el menú [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]Herramientas**de**, haga clic en **Opción**.</span><span class="sxs-lookup"><span data-stu-id="22586-126">To view the **General Options** dialog box, on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Tools** menu, click **Option**.</span></span>  
  
         <span data-ttu-id="22586-127">Y</span><span class="sxs-lookup"><span data-stu-id="22586-127">-AND-</span></span>  
  
    -   <span data-ttu-id="22586-128">La fecha especificada se encuentra entre el 1 de enero de 1753 y el 31 de diciembre de 9999.</span><span class="sxs-lookup"><span data-stu-id="22586-128">The date you enter is between January 1, 1753 and December 31, 9999.</span></span>  
  
-   <span data-ttu-id="22586-129">Si se realiza un seguimiento de los eventos con la utilidad **osql** o **sqlcmd** , agregue siempre **%** a los filtros de la columna de datos **TextData** .</span><span class="sxs-lookup"><span data-stu-id="22586-129">If tracing events from the **osql** utility or from the **sqlcmd** utility, always append **%** to filters on the **TextData** data column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22586-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="22586-130">See Also</span></span>  
 [<span data-ttu-id="22586-131">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="22586-131">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
