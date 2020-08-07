---
title: Crear una plantilla de seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
- saving trace template
ms.assetid: 025868b0-3790-4cda-8757-5a58327bfba0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 355f97c7fecd8a9e31f10de881d1ae6df3b8f122
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743747"
---
# <a name="create-a-trace-template-sql-server-profiler"></a><span data-ttu-id="8ec13-102">Crear una plantilla de seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="8ec13-102">Create a Trace Template (SQL Server Profiler)</span></span>
  <span data-ttu-id="8ec13-103">En este tema se describe cómo crear una plantilla de seguimiento nueva mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ec13-103">This topic describes how to create a new trace template by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-create-a-trace-template"></a><span data-ttu-id="8ec13-104">Para crear una plantilla de seguimiento</span><span class="sxs-lookup"><span data-stu-id="8ec13-104">To create a trace template</span></span>  
  
1.  <span data-ttu-id="8ec13-105">En el menú **Archivo** , haga clic en **Plantillas**y, a continuación, en **Nueva plantilla**.</span><span class="sxs-lookup"><span data-stu-id="8ec13-105">On the **File** menu, point to **Templates**, and then click **New Template**.</span></span>  
  
2.  <span data-ttu-id="8ec13-106">En el cuadro de diálogo **Propiedades de la plantilla de seguimiento** , seleccione un tipo de servidor en la lista **Seleccionar tipo de servidor**.</span><span class="sxs-lookup"><span data-stu-id="8ec13-106">In the **Trace Template Properties** dialog box, select a server type from the **Select server type**list.</span></span>  
  
3.  <span data-ttu-id="8ec13-107">En el cuadro **Nuevo nombre de plantilla** , escriba un nombre para la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8ec13-107">In the **New template name** box, enter a template name.</span></span>  
  
4.  <span data-ttu-id="8ec13-108">También puede hacer clic en **Basar plantilla nueva en una existente**y, a continuación, seleccionar una plantilla de la lista.</span><span class="sxs-lookup"><span data-stu-id="8ec13-108">Optionally, click **Base new template on existing one**, and then select a template from the list.</span></span>  
  
     <span data-ttu-id="8ec13-109">Todos los eventos, las columnas de datos y los filtros se establecen inicialmente tal como se especifica en la plantilla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8ec13-109">All events, data columns, and filters are initially set as specified in the selected template.</span></span>  
  
5.  <span data-ttu-id="8ec13-110">También puede hacer clic en **Usar como plantilla predeterminada para tipo de servidor seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="8ec13-110">Optionally, click **Use as a default template for selected server type**.</span></span>  
  
6.  <span data-ttu-id="8ec13-111">En la pestaña **Selección de eventos** , podrá agregar, quitar o modificar eventos, columnas de datos o filtros.</span><span class="sxs-lookup"><span data-stu-id="8ec13-111">On the **Events Selection** tab, add, remove, or modify events, data columns, or filters.</span></span>  
  
7.  <span data-ttu-id="8ec13-112">En el menú **Selección de eventos**, utilice el control de cuadrículas para agregar o quitar eventos y columnas de datos del archivo de seguimiento tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8ec13-112">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file as follows:</span></span>  
  
    -   <span data-ttu-id="8ec13-113">Para agregar un evento, expanda la categoría de evento correspondiente en la columna **Eventos** y seleccione el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="8ec13-113">To add an event, expand the appropriate event category in the **Events** column, and then select the event name.</span></span>  
  
    -   <span data-ttu-id="8ec13-114">Cuando se agrega un evento se incluyen de manera predeterminada todas las columnas de datos pertinentes.</span><span class="sxs-lookup"><span data-stu-id="8ec13-114">When you add an event, all relevant data columns are included by default.</span></span> <span data-ttu-id="8ec13-115">Para eliminar una columna de datos de un evento del seguimiento, desactive la casilla de la columna de datos del evento.</span><span class="sxs-lookup"><span data-stu-id="8ec13-115">To remove a data column for an event from a trace, clear the check box in the data column for the event.</span></span>  
  
    -   <span data-ttu-id="8ec13-116">Para agregar filtros, haga clic en el nombre de la columna de datos y especifique los criterios del filtro en el cuadro de diálogo **Editar filtro** .</span><span class="sxs-lookup"><span data-stu-id="8ec13-116">To add filters, click the data column name and specify the filter criteria in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="8ec13-117">También puede hacer clic con el botón derecho en el nombre de la columna de datos y hacer clic en **Editar filtro de columna** para abrir el cuadro de diálogo **Editar filtro** .</span><span class="sxs-lookup"><span data-stu-id="8ec13-117">You can also right-click the data column name, and click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="8ec13-118">Haga clic en **Aceptar** para agregar el filtro.</span><span class="sxs-lookup"><span data-stu-id="8ec13-118">Click **OK** to add the filter.</span></span>  
  
8.  <span data-ttu-id="8ec13-119">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8ec13-119">Click **Save.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ec13-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ec13-120">See Also</span></span>  
 <span data-ttu-id="8ec13-121">[Especificar eventos y columnas de datos para un archivo de seguimiento &#40;SQL Server Profiler&#41;](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="8ec13-121">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="8ec13-122">[Derivar una plantilla a partir de un seguimiento en ejecución &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="8ec13-122">[Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="8ec13-123">[Derivar una plantilla a partir de un archivo o tabla de seguimiento &#40;SQL Server Profiler&#41;](derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="8ec13-123">[Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="8ec13-124">[Plantillas y permisos de SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="8ec13-124">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="8ec13-125">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8ec13-125">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
