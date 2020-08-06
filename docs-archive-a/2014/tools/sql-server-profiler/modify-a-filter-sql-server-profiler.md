---
title: Modificar un filtro (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], modifying
- modifying filters, modifying
- filters [SQL Server], traces
ms.assetid: 8b317813-4918-4485-b930-77b1951aa00c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5a7bab18952820a3dc49c9479797a411521f8e71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671878"
---
# <a name="modify-a-filter-sql-server-profiler"></a><span data-ttu-id="acc74-102">Modificar un filtro (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="acc74-102">Modify a Filter (SQL Server Profiler)</span></span>
  <span data-ttu-id="acc74-103">Se agregan filtros a las plantillas de seguimiento, que contienen las definiciones de los seguimiento, para limitar el número de eventos que recopila un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="acc74-103">You add filters to trace templates, which contain the trace definitions, to limit the number of events that are gathered by a trace.</span></span> <span data-ttu-id="acc74-104">Esta limitación puede reducir las consecuencias sobre el rendimiento de las trazas.</span><span class="sxs-lookup"><span data-stu-id="acc74-104">Limiting the number of events gathered can reduce the performance effects of tracing.</span></span> <span data-ttu-id="acc74-105">Si establece filtros para una plantilla de seguimiento y averigua que el seguimiento no recopila el tipo de información que necesita, puede modificar el filtro.</span><span class="sxs-lookup"><span data-stu-id="acc74-105">If you set filters for a trace template and find that the trace is not gathering the kind of information that you need, you can edit the filter.</span></span>  
  
### <a name="to-modify-a-filter"></a><span data-ttu-id="acc74-106">Para modificar un filtro</span><span class="sxs-lookup"><span data-stu-id="acc74-106">To modify a filter</span></span>  
  
1.  <span data-ttu-id="acc74-107">En el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], abra la plantilla del filtro de seguimiento que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="acc74-107">In [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], open the template for the trace filter that you want to modify.</span></span> <span data-ttu-id="acc74-108">En el menú **Archivo** , haga clic en **Plantillas**y, a continuación, elija **Editar plantilla**.</span><span class="sxs-lookup"><span data-stu-id="acc74-108">On the **File** menu, click **Templates**, and then choose **Edit Template**.</span></span>  
  
2.  <span data-ttu-id="acc74-109">En la pestaña **General** del cuadro de diálogo **Propiedades de la plantilla de seguimiento** , seleccione una plantilla en la lista **Seleccionar nombre de plantilla** .</span><span class="sxs-lookup"><span data-stu-id="acc74-109">In the **General** tab of the **Trace Template Properties** dialog, select a template from the **Select template name** list.</span></span>  
  
3.  <span data-ttu-id="acc74-110">Haga clic en la pestaña **Selección de eventos** .</span><span class="sxs-lookup"><span data-stu-id="acc74-110">Click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="acc74-111">La pestaña **Selección de eventos** contiene un control de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="acc74-111">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="acc74-112">El control de cuadrícula es una tabla que contiene todas las clases de eventos en las que se puede realizar un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="acc74-112">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="acc74-113">La tabla contiene una fila para cada clase de evento.</span><span class="sxs-lookup"><span data-stu-id="acc74-113">The table contains one row for each event class.</span></span> <span data-ttu-id="acc74-114">Las clases de eventos pueden diferir ligeramente dependiendo del tipo y la versión del servidor al que esté conectado.</span><span class="sxs-lookup"><span data-stu-id="acc74-114">The event classes may differ slightly, depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="acc74-115">Las clases de eventos se identifican en la columna **Events**de la cuadrícula y se agrupan por categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="acc74-115">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="acc74-116">En las demás columnas se enumeran las columnas de datos que pueden devolverse para cada clase de evento.</span><span class="sxs-lookup"><span data-stu-id="acc74-116">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
4.  <span data-ttu-id="acc74-117">Haga clic en **Filtros de columna**.</span><span class="sxs-lookup"><span data-stu-id="acc74-117">Click **Column Filters**.</span></span>  
  
5.  <span data-ttu-id="acc74-118">En el cuadro de diálogo **Editar filtro** , haga clic en el valor junto al operador de comparación que desea modificar y escriba el valor nuevo o elimine un valor.</span><span class="sxs-lookup"><span data-stu-id="acc74-118">In the **Edit Filter** dialog box, click the value next to the comparison operator that you want to edit, and type the new value or delete a value.</span></span> <span data-ttu-id="acc74-119">También puede agregar otros filtros.</span><span class="sxs-lookup"><span data-stu-id="acc74-119">You can also add additional filters.</span></span>  
  
6.  <span data-ttu-id="acc74-120">Haga clic en **Aceptar** y guarde la plantilla.</span><span class="sxs-lookup"><span data-stu-id="acc74-120">Click **OK** and save the template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acc74-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="acc74-121">See Also</span></span>  
 [<span data-ttu-id="acc74-122">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="acc74-122">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
