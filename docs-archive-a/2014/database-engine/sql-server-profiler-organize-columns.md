---
title: SQL Server Profiler organizar columnas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.organize.columns.f1
ms.assetid: bf5674f4-da5e-43f9-aeb2-76ca37993790
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b63c2f7d882bac05fc6baf10614170ec23125c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748236"
---
# <a name="sql-server-profiler---organize-columns"></a><span data-ttu-id="892db-102">SQL Server Profiler (Organizar columnas)</span><span class="sxs-lookup"><span data-stu-id="892db-102">SQL Server Profiler - Organize Columns</span></span>
  <span data-ttu-id="892db-103">Utilice el cuadro de diálogo **Organizar columnas** para seleccionar columnas de datos y agrupar o agregar eventos que se muestran en un seguimiento; esto facilita la lectura y el análisis de los archivos o tablas de seguimiento grandes.</span><span class="sxs-lookup"><span data-stu-id="892db-103">Use the **Organize Columns** dialog box to select data columns for grouping or aggregating events that are displayed in a trace, which makes large trace files or tables easier to view and analyze.</span></span>  
  
 <span data-ttu-id="892db-104">La agregación mueve y contrae todos los eventos del seguimiento bajo su tipo de clase de evento correspondiente.</span><span class="sxs-lookup"><span data-stu-id="892db-104">Aggregating moves and collapses all events in the trace under its respective event class type.</span></span> <span data-ttu-id="892db-105">Aparece un signo más ( **+** ) a la izquierda del nombre de la clase de evento.</span><span class="sxs-lookup"><span data-stu-id="892db-105">A plus sign (**+**) appears to the left of the event class name.</span></span> <span data-ttu-id="892db-106">Si hace clic en el signo más, expande la clase de evento y puede ver todos sus eventos.</span><span class="sxs-lookup"><span data-stu-id="892db-106">Clicking the plus sign expands the event class so you can view all events of that type.</span></span>  
  
 <span data-ttu-id="892db-107">La agrupación organiza todas las clases de evento de un tipo específico en una ventana de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="892db-107">Grouping organizes all event classes of a specific type together in the trace window display.</span></span> <span data-ttu-id="892db-108">Sin embargo, los eventos no se contraen bajo el tipo de clase de evento.</span><span class="sxs-lookup"><span data-stu-id="892db-108">However, the events are not collapsed under the event class type.</span></span>  
  
 <span data-ttu-id="892db-109">Cuando agrupa o agrega eventos en una ventana de seguimiento, las columnas seleccionadas para agrupar o agregar permanecen fijas en la ventana, pero puede desplazarse a la derecha o la izquierda para ver las demás columnas de datos.</span><span class="sxs-lookup"><span data-stu-id="892db-109">When you group or aggregate events in a trace window display, the columns selected for grouping or aggregating remain fixed in the display window, but you can scroll to the right or left to view all other data columns.</span></span>  
  
 <span data-ttu-id="892db-110">Para tener acceso a este cuadro de diálogo, abra un archivo o una tabla de seguimiento existente y haga clic en **Propiedades** en el menú [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] **Archivo** de .</span><span class="sxs-lookup"><span data-stu-id="892db-110">To access this dialog box, open an existing trace file or table, and click **Properties** on the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] **File** menu.</span></span> <span data-ttu-id="892db-111">En el cuadro de diálogo **Propiedades de seguimiento** , haga clic en la pestaña **Selección de eventos** y, a continuación, haga clic en **Organizar columnas**.</span><span class="sxs-lookup"><span data-stu-id="892db-111">In the **Trace Properties** dialog box, click the **Events Selection** tab, and then click **Organize Columns**.</span></span> <span data-ttu-id="892db-112">También puede hacer clic en **Organizar columnas** en la pestaña **Selección de eventos** cuando crea un nuevo seguimiento.</span><span class="sxs-lookup"><span data-stu-id="892db-112">You can also click **Organize Columns** on the **Events Selection** tab when you are creating a new trace.</span></span>  
  
## <a name="options"></a><span data-ttu-id="892db-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="892db-113">Options</span></span>  
 <span data-ttu-id="892db-114">**Grupos**</span><span class="sxs-lookup"><span data-stu-id="892db-114">**Groups**</span></span>  
 <span data-ttu-id="892db-115">Desplaza los nombres de columnas de datos bajo **Grupos** para agrupar o agregar clases de eventos en la ventana de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="892db-115">Move data column names under **Groups** to group or aggregate event classes in the trace window.</span></span>  
  
 <span data-ttu-id="892db-116">Para agregar eventos, desplace una columna de datos a **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="892db-116">To aggregate events, move one data column into **Groups**.</span></span> <span data-ttu-id="892db-117">De este modo, todos los eventos de un tipo específico se contraen bajo el nombre del tipo de clase de evento en la ventana de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="892db-117">This causes all events of a specific type to be collapsed under event class type name in the trace window display.</span></span> <span data-ttu-id="892db-118">Aparece un signo más ( **+** ) a la izquierda del nombre de la clase de evento.</span><span class="sxs-lookup"><span data-stu-id="892db-118">A plus sign (**+**) appears to the left of the event class name.</span></span> <span data-ttu-id="892db-119">Haga clic en el signo más para expandir el tipo de clase de evento y ver todos sus eventos.</span><span class="sxs-lookup"><span data-stu-id="892db-119">Click the plus sign to expand the event class type and view all events.</span></span> <span data-ttu-id="892db-120">Puede activar y desactivar la agregación y la agrupación si hace clic en **Vista agregada** o **Vista agrupada** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="892db-120">You can set aggregation and grouping on and off by clicking **Aggregated View** or **Grouped View** on the **View** menu.</span></span>  
  
 <span data-ttu-id="892db-121">Para agrupar eventos, desplace varias columnas de datos a **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="892db-121">To group events, move more than one data column into **Groups**.</span></span> <span data-ttu-id="892db-122">De este modo, todos los eventos de un tipo específico se agrupan en la ventana de seguimiento, pero no se contraen bajo el nombre del tipo de clase de evento.</span><span class="sxs-lookup"><span data-stu-id="892db-122">This causes all events of a specific type to be grouped together in the trace window display, but does not collapse the events under each event class type name.</span></span> <span data-ttu-id="892db-123">Puede cambiar entre una vista agrupada y una vista no agrupada si hace clic en **Vista agrupada** en el menú Ver.</span><span class="sxs-lookup"><span data-stu-id="892db-123">You can switch back and forth between a grouped view and an ungrouped view by clicking **Grouped View** on the View menu.</span></span> <span data-ttu-id="892db-124">Cuando se desplaza más de una columna de datos a **Grupos**, la opción para cambiar a **Vista agregada** deja de estar disponible.</span><span class="sxs-lookup"><span data-stu-id="892db-124">When more than one data column is moved into **Groups**, the option to switch to **Aggregated View** is not available.</span></span>  
  
 <span data-ttu-id="892db-125">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="892db-125">**Columns**</span></span>  
 <span data-ttu-id="892db-126">Muestra las columnas de datos que se pueden desplazar a **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="892db-126">List of data columns available to move into **Groups**.</span></span> <span data-ttu-id="892db-127">Haga clic en el signo más ( **+** ) situado a la izquierda de **columnas** para expandir la lista.</span><span class="sxs-lookup"><span data-stu-id="892db-127">Click the plus sign (**+**) to the left of **Columns** to expand the list.</span></span>  
  
 <span data-ttu-id="892db-128">**Arriba**</span><span class="sxs-lookup"><span data-stu-id="892db-128">**Up**</span></span>  
 <span data-ttu-id="892db-129">Después de seleccionar una columna de datos, haga clic en **Subir** para subir las columnas a **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="892db-129">After selecting a data column, click **Up** to move data columns up into **Groups**.</span></span> <span data-ttu-id="892db-130">También puede hacer clic en **Subir** para volver a organizar la visualización de las columnas en la ventana de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="892db-130">You can also click **Up** to rearrange the display of columns in the trace window display.</span></span>  
  
 <span data-ttu-id="892db-131">**Bajar**</span><span class="sxs-lookup"><span data-stu-id="892db-131">**Down**</span></span>  
 <span data-ttu-id="892db-132">Después de seleccionar una columna de datos, haga clic en **Bajar** para quitar las columnas de **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="892db-132">After selecting a data column, click **Down** to move data columns out of **Groups**.</span></span> <span data-ttu-id="892db-133">También puede hacer clic en **Bajar** para volver a organizar la visualización de las columnas en la ventana de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="892db-133">You can also click **Down** to rearrange the display of columns in the trace window display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="892db-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="892db-134">See Also</span></span>  
 <span data-ttu-id="892db-135">[Organizar las columnas mostradas en un SQL Server Profiler de seguimiento &#40;&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="892db-135">[Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="892db-136">[Cree un SQL Server Profiler de &#40;de seguimiento&#41;](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="892db-136">[Create a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="892db-137">[Crear una plantilla de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/create-a-trace-template-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="892db-137">[Create a Trace Template &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/create-a-trace-template-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="892db-138">[Abra un archivo de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="892db-138">[Open a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="892db-139">Abrir una tabla de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="892db-139">Open a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md)  
  
  