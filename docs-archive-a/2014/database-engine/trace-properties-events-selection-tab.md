---
title: Propiedades de seguimiento (pestaña selección de eventos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.traceproperties.eventsselection.f1
helpviewer_keywords:
- Trace Properties dialog box
ms.assetid: e1892f24-7272-4d5d-8926-6150cc82b2c3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11f4725865d39c21e36f5fd09eaf2afd4cde3017
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747157"
---
# <a name="trace-properties-events-selection-tab"></a><span data-ttu-id="aa940-102">Propiedades de seguimiento (pestaña Selección de eventos)</span><span class="sxs-lookup"><span data-stu-id="aa940-102">Trace Properties (Events Selection Tab)</span></span>
  <span data-ttu-id="aa940-103">Utilice la pestaña **Selección de eventos** del cuadro de diálogo **Propiedades de seguimiento** para ver o especificar columnas de datos y eventos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="aa940-103">Use the **Events Selection** tab of the **Trace Properties** dialog box to view or specify traced events and data columns.</span></span>  
  
## <a name="options"></a><span data-ttu-id="aa940-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="aa940-104">Options</span></span>  
 <span data-ttu-id="aa940-105">Columna**Eventos**</span><span class="sxs-lookup"><span data-stu-id="aa940-105">**Events** column</span></span>  
 <span data-ttu-id="aa940-106">Especifique los eventos de seguimiento seleccionando o desactivando la casilla de la columna de eventos.</span><span class="sxs-lookup"><span data-stu-id="aa940-106">Specify traced events by selecting or clearing the check box in the event column.</span></span> <span data-ttu-id="aa940-107">Los**eventos** se organizan por categoría.</span><span class="sxs-lookup"><span data-stu-id="aa940-107">**Events** are organized by event category.</span></span> <span data-ttu-id="aa940-108">Las clases de evento especificadas en la plantilla se seleccionan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="aa940-108">Event classes specified in the template are automatically selected.</span></span> <span data-ttu-id="aa940-109">Para obtener más información, consulte [Referencia de las clase de eventos de SQL Server](../relational-databases/event-classes/sql-server-event-class-reference.md).</span><span class="sxs-lookup"><span data-stu-id="aa940-109">For more information, see [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span></span>  
  
 <span data-ttu-id="aa940-110">Columnas de datos</span><span class="sxs-lookup"><span data-stu-id="aa940-110">Data columns</span></span>  
 <span data-ttu-id="aa940-111">Especifique las columnas de datos de seguimiento activando la casilla que se corresponda con el evento y la columna de datos necesarios.</span><span class="sxs-lookup"><span data-stu-id="aa940-111">Specify traced data columns by checking the box that corresponds with the event and the data column you need.</span></span> <span data-ttu-id="aa940-112">Todas las columnas de eventos importantes se activan de manera predeterminada en cada evento incluido en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="aa940-112">All relevant event columns are checked by default for each event included in the trace.</span></span>  
  
 <span data-ttu-id="aa940-113">Especifique los filtros haciendo clic en el encabezado de la columna de datos y especificando los criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="aa940-113">Specify filters by clicking the data column heading and entering the filter criteria.</span></span> <span data-ttu-id="aa940-114">Las columnas de datos filtradas se indican mediante un icono de filtro situado a la izquierda de la etiqueta de columna en el cuadro de diálogo **Editar filtro** .</span><span class="sxs-lookup"><span data-stu-id="aa940-114">Filtered data columns are indicated by a filter icon to the left of the column label in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="aa940-115">Para obtener más información, vea [SQL Server Profiler (Editar filtro)](../../2014/database-engine/sql-server-profiler-edit-filter.md).</span><span class="sxs-lookup"><span data-stu-id="aa940-115">For more information, see [SQL Server Profiler - Edit Filter](../../2014/database-engine/sql-server-profiler-edit-filter.md).</span></span>  
  
 <span data-ttu-id="aa940-116">**Mostrar todos los eventos**</span><span class="sxs-lookup"><span data-stu-id="aa940-116">**Show all events**</span></span>  
 <span data-ttu-id="aa940-117">Se muestran todos los eventos disponibles.</span><span class="sxs-lookup"><span data-stu-id="aa940-117">Show all available events.</span></span> <span data-ttu-id="aa940-118">De forma predeterminada, solo se muestran las filas de la cuadrícula **Selección de eventos** que están seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="aa940-118">By default, only rows in the **Events Selection** grid that are selected display.</span></span> <span data-ttu-id="aa940-119">Desactive esta casilla para ocultar todos los eventos que no estén seleccionados en la cuadrícula **Selección de eventos** .</span><span class="sxs-lookup"><span data-stu-id="aa940-119">Uncheck this box to hide all unselected events in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="aa940-120">**Mostrar todas las columnas**</span><span class="sxs-lookup"><span data-stu-id="aa940-120">**Show all columns**</span></span>  
 <span data-ttu-id="aa940-121">Muestra todas las columnas de datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="aa940-121">Show all available data columns.</span></span> <span data-ttu-id="aa940-122">De forma predeterminada, solo se muestran las columnas de datos seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="aa940-122">By default, only data columns that are selected display.</span></span> <span data-ttu-id="aa940-123">Desactive esta casilla para ocultar todas las columnas de datos que no estén seleccionadas en la cuadrícula **Selección de eventos** .</span><span class="sxs-lookup"><span data-stu-id="aa940-123">Uncheck this box to hide all unselected data columns in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="aa940-124">**Filtros de columnas**</span><span class="sxs-lookup"><span data-stu-id="aa940-124">**Column Filters**</span></span>  
 <span data-ttu-id="aa940-125">Inicia el cuadro de diálogo **Editar filtro** .</span><span class="sxs-lookup"><span data-stu-id="aa940-125">Launches the **Edit Filter** dialog box.</span></span> <span data-ttu-id="aa940-126">Puede utilizar este cuadro de diálogo para editar filtros de columnas de datos.</span><span class="sxs-lookup"><span data-stu-id="aa940-126">You can use this dialog to edit data column filters.</span></span>  
  
 <span data-ttu-id="aa940-127">**Organizar columnas**</span><span class="sxs-lookup"><span data-stu-id="aa940-127">**Organize Columns**</span></span>  
 <span data-ttu-id="aa940-128">Cambia el orden de las columnas del seguimiento y agrupa los resultados en una o más columnas.</span><span class="sxs-lookup"><span data-stu-id="aa940-128">Changes the order of columns in the trace and groups results by one or more columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa940-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa940-129">See Also</span></span>  
 <span data-ttu-id="aa940-130">[Especificar eventos y columnas de datos para un archivo de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="aa940-130">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="aa940-131">[Organizar las columnas mostradas en un SQL Server Profiler de seguimiento &#40;&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="aa940-131">[Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="aa940-132">[Filtrar eventos en un SQL Server Profiler de seguimiento &#40;&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="aa940-132">[Filter Events in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="aa940-133">[Ver información de filtro &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="aa940-133">[View Filter Information &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="aa940-134">[Modificar un filtro &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="aa940-134">[Modify a Filter &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="aa940-135">[Plantillas y permisos de SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="aa940-135">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="aa940-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="aa940-136">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
