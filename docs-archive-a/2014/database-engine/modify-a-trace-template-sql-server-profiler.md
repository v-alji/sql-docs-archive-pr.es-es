---
title: Modificar una plantilla de seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
- modifying traces
ms.assetid: b81df2a1-e202-43d8-92b0-0beb145f0116
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2a93baedb1875ac740e74065ae7188f9b576e083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663656"
---
# <a name="modify-a-trace-template-sql-server-profiler"></a><span data-ttu-id="87773-102">Modificar una plantilla de seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="87773-102">Modify a Trace Template (SQL Server Profiler)</span></span>
  <span data-ttu-id="87773-103">En este tema se explica cómo modificar una plantilla de seguimiento mediante [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87773-103">This topic describes how to modify a trace template by using [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-modify-a-trace-template"></a><span data-ttu-id="87773-104">Para modificar una plantilla de seguimiento</span><span class="sxs-lookup"><span data-stu-id="87773-104">To modify a trace template</span></span>  
  
1.  <span data-ttu-id="87773-105">En el menú **Archivo** , seleccione **Plantillas**y haga clic en **Editar plantilla**.</span><span class="sxs-lookup"><span data-stu-id="87773-105">On the **File** menu, point to **Templates**, and then click **Edit Template**.</span></span>  
  
2.  <span data-ttu-id="87773-106">En el cuadro de diálogo **Propiedades de la plantilla de seguimiento** , en la pestaña **General** , modifique el tipo de servidor y el nombre de la plantilla si es necesario o elija una plantilla predeterminada para el tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="87773-106">In the **Trace Template Properties** dialog box, on the **General** tab, you can modify the server type and template name, or choose to use a default template for the server type.</span></span>  
  
3.  <span data-ttu-id="87773-107">En la pestaña **selección de eventos**, utilice el control de cuadrícula para agregar o quitar eventos y columnas de datos del archivo de seguimiento como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="87773-107">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file as follows.</span></span>  
  
    -   <span data-ttu-id="87773-108">Para agregar un evento, expanda la categoría de evento correspondiente en la columna **Eventos** y seleccione el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="87773-108">To add an event, expand the appropriate event category in the **Events** column, and then select the event name.</span></span>  
  
    -   <span data-ttu-id="87773-109">Cuando se agrega un evento se incluyen de manera predeterminada todas las columnas de datos pertinentes.</span><span class="sxs-lookup"><span data-stu-id="87773-109">When you add an event, all relevant data columns are included by default.</span></span> <span data-ttu-id="87773-110">Para eliminar una columna de datos de un evento del seguimiento, desactive la casilla de la columna de datos del evento.</span><span class="sxs-lookup"><span data-stu-id="87773-110">To remove a data column for an event from a trace, clear the check box in the data column for the event.</span></span>  
  
    -   <span data-ttu-id="87773-111">Para agregar filtros, haga clic en el nombre de la columna de datos y especifique los criterios del filtro en el cuadro de diálogo **Editar filtro** .</span><span class="sxs-lookup"><span data-stu-id="87773-111">To add filters, click the data column name and specify the filter criteria in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="87773-112">También puede hacer clic con el botón derecho en el nombre de la columna de datos y hacer clic en **Editar filtro de columna** para abrir el cuadro de diálogo **Editar filtro** .</span><span class="sxs-lookup"><span data-stu-id="87773-112">You can also right-click the data column name, and click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="87773-113">Haga clic en **Aceptar** para agregar el filtro.</span><span class="sxs-lookup"><span data-stu-id="87773-113">Click **OK** to add the filter.</span></span>  
  
4.  <span data-ttu-id="87773-114">Haga clic en **Guardar**o bien en **Guardar As**si desea guardar la plantilla de seguimiento con otro nombre.</span><span class="sxs-lookup"><span data-stu-id="87773-114">Click **Save**, or click **Save As**to save the trace template under another name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87773-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87773-115">See Also</span></span>  
 <span data-ttu-id="87773-116">[Especificar eventos y columnas de datos para un archivo de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="87773-116">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="87773-117">[Derivar una plantilla a partir de un seguimiento en ejecución &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="87773-117">[Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="87773-118">[Derivar una plantilla a partir de un archivo o tabla de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="87773-118">[Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="87773-119">[Plantillas y permisos de SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="87773-119">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="87773-120">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="87773-120">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
