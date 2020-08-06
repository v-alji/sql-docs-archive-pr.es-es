---
title: Crear un seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], creating
ms.assetid: 0302fa6d-d2b5-43fe-ad70-7a337575b112
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7d73333bbf0ba985ed4952e03584b4e4c130ab6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743756"
---
# <a name="create-a-trace-sql-server-profiler"></a><span data-ttu-id="151ee-102">Crear un seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="151ee-102">Create a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="151ee-103">En este tema se describe cómo utilizar [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para crear un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="151ee-103">This topic describes how to use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to create a trace.</span></span>  
  
### <a name="to-create-a-trace"></a><span data-ttu-id="151ee-104">Para crear un seguimiento</span><span class="sxs-lookup"><span data-stu-id="151ee-104">To create a trace</span></span>  
  
1.  <span data-ttu-id="151ee-105">En el menú **Archivo** , haga clic en **Nueva seguimiento**y conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="151ee-105">On the **File** menu, click **New Trace**, and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="151ee-106">Aparecerá el cuadro de diálogo **Propiedades de seguimiento** .</span><span class="sxs-lookup"><span data-stu-id="151ee-106">The **Trace Properties** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="151ee-107">Si se ha seleccionado **Iniciar el seguimiento inmediatamente tras realizar la conexión** , no aparecerá el cuadro de diálogo **Propiedades de seguimiento** y, en su lugar, se iniciará el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="151ee-107">The **Trace Properties** dialog box fails to appear, and the trace begins instead, if **Start tracing immediately after making connection** is selected.</span></span> <span data-ttu-id="151ee-108">Para desactivar esta configuración, en el menú **Herramientas**, haga clic en **Opciones**y desactive la casilla **Iniciar el seguimiento inmediatamente tras realizar la conexión** .</span><span class="sxs-lookup"><span data-stu-id="151ee-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="151ee-109">En el cuadro **Nombre de seguimiento** , escriba un nombre para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="151ee-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="151ee-110">En la lista **Usar la plantilla** , seleccione la plantilla de seguimiento que desea utilizar para el seguimiento o seleccione la opción **En blanco** si no desea utilizar ninguna plantilla.</span><span class="sxs-lookup"><span data-stu-id="151ee-110">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="151ee-111">Para guardar los resultados del seguimiento, realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="151ee-111">To save the trace results, do one of the following:</span></span>  
  
    -   <span data-ttu-id="151ee-112">Haga clic en **Guardar en el archivo**para capturar el seguimiento a un archivo.</span><span class="sxs-lookup"><span data-stu-id="151ee-112">Click **Save to file**to capture the trace to a file.</span></span> <span data-ttu-id="151ee-113">Especifique un valor en **Establecer el tamaño máximo de archivo (MB)** .</span><span class="sxs-lookup"><span data-stu-id="151ee-113">Specify a value for **Set maximum file size**.</span></span> <span data-ttu-id="151ee-114">El valor predeterminado es 5 megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="151ee-114">The default value is 5 megabytes (MB).</span></span>  
  
         <span data-ttu-id="151ee-115">También puede seleccionar **Habilitar sustitución incremental de archivos** para crear automáticamente nuevos archivos cuando se alcance el tamaño máximo del archivo</span><span class="sxs-lookup"><span data-stu-id="151ee-115">Optionally, select **Enable file rollover** to automatically create new files when the maximum file size is reached.</span></span> <span data-ttu-id="151ee-116">También puede seleccionar **El servidor procesa los datos de seguimiento**, que hace que el servicio que ejecuta el seguimiento procese los datos del seguimiento en lugar de la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="151ee-116">You can also optionally select **Server processes trace data**, which causes the service that is running the trace to process trace data instead of the client application.</span></span> <span data-ttu-id="151ee-117">Cuando el servidor procese los datos del seguimiento, no se omitirá ningún evento en condiciones de gran demanda; sin embargo, puede que el rendimiento del servidor se vea afectado.</span><span class="sxs-lookup"><span data-stu-id="151ee-117">When the server processes trace data, no events are skipped even under stress conditions, but server performance may be affected.</span></span>  
  
    -   <span data-ttu-id="151ee-118">Haga clic en **Guardar en tabla** para capturar el seguimiento en una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="151ee-118">Click **Save to table** to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="151ee-119">Si lo desea, haga clic en **Establecer número máximo de filas**y especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="151ee-119">Optionally, click **Set maximum rows**, and specify a value.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="151ee-120">Si no guarda los resultados del seguimiento puede en un archivo o una tabla, podrá ver el seguimiento mientras el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] esté abierto.</span><span class="sxs-lookup"><span data-stu-id="151ee-120">When you do not save the trace results to a file or table, you can view the trace while [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is open.</span></span> <span data-ttu-id="151ee-121">No obstante, perderá los resultados del seguimiento al detenerlo y cerrar el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="151ee-121">However, you lose the trace results after you stop the trace and close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="151ee-122">Para evitarlo, haga clic en la opción **Guardar** del menú **Archivo** para guardar los resultados antes de cerrar el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="151ee-122">To avoid losing the trace results in this way, click **Save** on the **File** menu to save the results before you close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
5.  <span data-ttu-id="151ee-123">Opcionalmente, active la casilla **Habilitar hora de detención de seguimiento** para especificar una fecha y hora de detención.</span><span class="sxs-lookup"><span data-stu-id="151ee-123">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="151ee-124">Para agregar o quitar eventos, columnas de datos o filtros, haga clic en la pestaña **Selección de eventos**.</span><span class="sxs-lookup"><span data-stu-id="151ee-124">To add or remove events, data columns or filters, click the **Events Selection**tab.</span></span> <span data-ttu-id="151ee-125">Para obtener más información, vea [Especificar eventos y columnas de datos para un archivo de seguimiento &#40;SQL Server Profiler&#41;](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="151ee-125">For more information, see: [Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](sql-server-profiler.md)</span></span>  
  
7.  <span data-ttu-id="151ee-126">Haga clic en **Ejecutar** para iniciar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="151ee-126">Click **Run** to start the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="151ee-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="151ee-127">See Also</span></span>  
 <span data-ttu-id="151ee-128">[Permisos necesarios para ejecutar SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="151ee-128">[Permissions Required to Run SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="151ee-129">[Plantillas y permisos de SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="151ee-129">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 <span data-ttu-id="151ee-130">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="151ee-130">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="151ee-131">Establecer correlaciones de un seguimiento con datos del registro de rendimiento de Windows &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="151ee-131">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/correlate-a-trace-with-windows-performance-log-data-sql-server-profiler.md)  
  
  
