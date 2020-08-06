---
title: Propiedades de la plantilla de seguimiento (pestaña selección de eventos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.tracetemplateproperties.eventsselection.f1
helpviewer_keywords:
- Trace Template Properties dialog box
ms.assetid: 5b202457-ab42-4902-8012-7f3f40aa09f5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: da497db6e9373c63836753dc2be96deb3ce90244
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749426"
---
# <a name="trace-template-properties-events-selection-tab"></a><span data-ttu-id="6afd5-102">Propiedades de la plantilla de seguimiento (pestaña Selección de eventos)</span><span class="sxs-lookup"><span data-stu-id="6afd5-102">Trace Template Properties (Events Selection Tab)</span></span>
  <span data-ttu-id="6afd5-103">Utilice la pestaña **Selección de eventos** del cuadro de diálogo **Propiedades de la plantilla de seguimiento** para ver, editar o especificar las clases de eventos y las columnas de datos que se van a incluir en una plantilla de seguimiento del [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6afd5-103">Use the **Events Selection** tab of the **Trace Template Properties** dialog box to view, edit, or specify event classes and data columns to include in a [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace template.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6afd5-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="6afd5-104">Options</span></span>  
 <span data-ttu-id="6afd5-105">Columna**Eventos**</span><span class="sxs-lookup"><span data-stu-id="6afd5-105">**Events** column</span></span>  
 <span data-ttu-id="6afd5-106">Active o desactive la casilla de la columna de eventos para especificar los eventos de los que debe realizarse un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6afd5-106">Specify events that should be traced by selecting or clearing the check box in the event column.</span></span> <span data-ttu-id="6afd5-107">Los eventos se organizan por categoría.</span><span class="sxs-lookup"><span data-stu-id="6afd5-107">Events are organized by event category.</span></span>  
  
 <span data-ttu-id="6afd5-108">Si ha seleccionado **Basar plantilla nueva en una existente** en la pestaña **General** , los eventos se seleccionan automáticamente de acuerdo con la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="6afd5-108">If you selected **Base new template on existing one** on the **General** tab, events are automatically selected according to the specified template.</span></span> <span data-ttu-id="6afd5-109">Para obtener más información sobre las clases de eventos, vea [Referencia de las clase de eventos de SQL Server](../relational-databases/event-classes/sql-server-event-class-reference.md).</span><span class="sxs-lookup"><span data-stu-id="6afd5-109">For more information about event classes, see [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span></span>  
  
 <span data-ttu-id="6afd5-110">Columnas de datos</span><span class="sxs-lookup"><span data-stu-id="6afd5-110">Data columns</span></span>  
 <span data-ttu-id="6afd5-111">Especifique las columnas de datos de las que debe realizarse un seguimiento activando el cuadro correspondiente al evento y la columna de datos que necesite.</span><span class="sxs-lookup"><span data-stu-id="6afd5-111">Specify data columns that should be traced by checking the box that corresponds with the event and the data column you need.</span></span> <span data-ttu-id="6afd5-112">Si se activa la casilla correspondiente al evento, todas las columnas de eventos pertinentes se activan de forma predeterminada para cada evento incluido en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6afd5-112">All relevant event columns are checked by default for each event included in the trace, if the checkbox corresponding to the event is checked.</span></span> <span data-ttu-id="6afd5-113">Si ha seleccionado **Basar plantilla nueva en una existente** en la pestaña **General** , las columnas de datos y los filtros se seleccionan automáticamente de acuerdo con la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="6afd5-113">If you checked **Base new template on existing one** on the **General** tab, data columns and filters are automatically selected according to the specified template.</span></span>  
  
 <span data-ttu-id="6afd5-114">Especifique los filtros haciendo clic en el encabezado de la columna de datos y especificando los criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="6afd5-114">Specify filters by clicking the data column heading and entering the filter criteria.</span></span> <span data-ttu-id="6afd5-115">Las columnas de datos filtradas se indican mediante un icono de filtro situado a la izquierda de la etiqueta de columna en el cuadro de diálogo **Editar filtro** .</span><span class="sxs-lookup"><span data-stu-id="6afd5-115">Filtered data columns are indicated by a filter icon to the left of the column label in the **Edit Filter** dialog box.</span></span>  
  
 <span data-ttu-id="6afd5-116">**Mostrar todos los eventos**</span><span class="sxs-lookup"><span data-stu-id="6afd5-116">**Show all events**</span></span>  
 <span data-ttu-id="6afd5-117">Se muestran todos los eventos disponibles.</span><span class="sxs-lookup"><span data-stu-id="6afd5-117">Show all available events.</span></span> <span data-ttu-id="6afd5-118">Esta opción está activada de forma predeterminada si crea una nueva plantilla que no se base en una plantilla existente.</span><span class="sxs-lookup"><span data-stu-id="6afd5-118">This option is checked by default if you are creating a new template that is not based on an existing template.</span></span> <span data-ttu-id="6afd5-119">Desactive esta opción para ocultar todos los eventos no seleccionados en la cuadrícula **Selección de eventos** .</span><span class="sxs-lookup"><span data-stu-id="6afd5-119">Uncheck to hide all unselected events in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="6afd5-120">**Mostrar todas las columnas**</span><span class="sxs-lookup"><span data-stu-id="6afd5-120">**Show all columns**</span></span>  
 <span data-ttu-id="6afd5-121">Muestra todas las columnas de datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="6afd5-121">Show all available data columns.</span></span> <span data-ttu-id="6afd5-122">Esta opción está activada de forma predeterminada si crea una nueva plantilla que no se base en una plantilla existente.</span><span class="sxs-lookup"><span data-stu-id="6afd5-122">This option is checked by default if you are creating a new template that is not based on an existing template.</span></span> <span data-ttu-id="6afd5-123">Desactive esta opción para ocultar todas las columnas de datos no seleccionadas en la cuadrícula **Selección de eventos** .</span><span class="sxs-lookup"><span data-stu-id="6afd5-123">Uncheck to hide all unselected data columns in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="6afd5-124">**Filtros de columnas**</span><span class="sxs-lookup"><span data-stu-id="6afd5-124">**Column Filters**</span></span>  
 <span data-ttu-id="6afd5-125">Inicia el cuadro de diálogo **Editar filtro**, que muestra un icono de filtro a la izquierda de la etiqueta de columna de datos.</span><span class="sxs-lookup"><span data-stu-id="6afd5-125">Launches the **Edit Filter** dialog box, which displays a filter icon to the left of the data column label.</span></span> <span data-ttu-id="6afd5-126">Utilice el cuadro de diálogo **Editar filtro** para editar los filtros de las columnas de datos.</span><span class="sxs-lookup"><span data-stu-id="6afd5-126">Use the **Edit Filter** dialog box to edit data column filters.</span></span>  
  
 <span data-ttu-id="6afd5-127">**Organizar columnas**</span><span class="sxs-lookup"><span data-stu-id="6afd5-127">**Organize Columns**</span></span>  
 <span data-ttu-id="6afd5-128">Cambia el orden de las columnas del seguimiento y agrupa los resultados en una o más columnas.</span><span class="sxs-lookup"><span data-stu-id="6afd5-128">Changes the order of columns in the trace and groups results by one or more columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6afd5-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6afd5-129">See Also</span></span>  
 <span data-ttu-id="6afd5-130">[Especificar eventos y columnas de datos para un archivo de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6afd5-130">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="6afd5-131">[Organizar las columnas mostradas en un SQL Server Profiler de seguimiento &#40;&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6afd5-131">[Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="6afd5-132">[Filtrar eventos en un SQL Server Profiler de seguimiento &#40;&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6afd5-132">[Filter Events in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="6afd5-133">[Ver información de filtro &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6afd5-133">[View Filter Information &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="6afd5-134">[Modificar un filtro &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6afd5-134">[Modify a Filter &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="6afd5-135">[Plantillas y permisos de SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="6afd5-135">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="6afd5-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="6afd5-136">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
