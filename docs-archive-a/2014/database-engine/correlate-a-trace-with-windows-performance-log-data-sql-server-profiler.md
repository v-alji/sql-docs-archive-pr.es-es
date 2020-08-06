---
title: Correlacionar un seguimiento con los datos del registro de rendimiento de Windows (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], logs
ms.assetid: e1b3072c-8daf-49a7-9895-c8cccd2adb95
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 34575cf4270d817ecfbb5b2d1824831cc99454fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673257"
---
# <a name="correlate-a-trace-with-windows-performance-log-data-sql-server-profiler"></a><span data-ttu-id="203ac-102">Establecer correlaciones de un seguimiento con datos del registro de rendimiento de Windows (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="203ac-102">Correlate a Trace with Windows Performance Log Data (SQL Server Profiler)</span></span>
  [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]<span data-ttu-id="203ac-103">puede poner en correlación los contadores del monitor de sistema de Microsoft Windows con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] eventos o.</span><span class="sxs-lookup"><span data-stu-id="203ac-103">can correlate Microsoft Windows System Monitor counters with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] events.</span></span> <span data-ttu-id="203ac-104">El Monitor del sistema de Windows registra la actividad del sistema para contadores específicos en registros de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="203ac-104">Windows System Monitor logs system activity for specified counters in performance logs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="203ac-105">Para obtener más información acerca de compartir registros entre diferentes versiones de Windows, vea el procedimiento al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="203ac-105">For information about sharing logs among different versions of Windows, see the procedure at the end of this topic.</span></span>  
  
### <a name="to-correlate-a-trace-with-performance-log-data"></a><span data-ttu-id="203ac-106">Para establecer correlaciones de un seguimiento con datos del registro de rendimiento</span><span class="sxs-lookup"><span data-stu-id="203ac-106">To correlate a trace with performance log data</span></span>  
  
1.  <span data-ttu-id="203ac-107">En [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], abra un archivo de seguimiento o una tabla de seguimiento guardados.</span><span class="sxs-lookup"><span data-stu-id="203ac-107">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], open a saved trace file or trace table.</span></span> <span data-ttu-id="203ac-108">No puede establecer correlaciones de un seguimiento en ejecución que aún está recopilando datos de eventos.</span><span class="sxs-lookup"><span data-stu-id="203ac-108">You cannot correlate a running trace that is still collecting event data.</span></span> <span data-ttu-id="203ac-109">Para lograr una correlación precisa con los datos del Monitor de sistema, el seguimiento debe contener las columnas de datos **StartTime** y **EndTime** .</span><span class="sxs-lookup"><span data-stu-id="203ac-109">For accurate correlation with System Monitor data, the trace must contain both **StartTime** and **EndTime** data columns.</span></span>  
  
2.  <span data-ttu-id="203ac-110">En el menú  **Archivo** de [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], haga clic en **Importar datos de rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="203ac-110">On the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] **File** menu, click **Import Performance Data**.</span></span>  
  
3.  <span data-ttu-id="203ac-111">En el cuadro de diálogo **Abrir** , seleccione un archivo que contenga un registro de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="203ac-111">In the **Open** dialog box, select a file that contains a performance log.</span></span> <span data-ttu-id="203ac-112">Los datos del registro de rendimiento deben haber sido capturados durante el mismo período de tiempo en que se capturaron los datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="203ac-112">The performance log data must have been captured during the same time period in which the trace data is captured.</span></span>  
  
4.  <span data-ttu-id="203ac-113">En el cuadro de diálogo **Límite de contadores de rendimiento** , active las casillas que corresponden a los objetos y contadores del Monitor del sistema que desea mostrar junto con el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="203ac-113">In the **Performance Counters Limit** dialog box, select the check boxes that correspond to the System Monitor objects and counters that you want to display alongside the trace.</span></span> <span data-ttu-id="203ac-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="203ac-114">Click **OK.**</span></span>  
  
5.  <span data-ttu-id="203ac-115">Seleccione un evento en la ventana de eventos de seguimiento o navegue por varias filas adyacentes en la ventana de eventos de seguimiento utilizando las teclas de flecha.</span><span class="sxs-lookup"><span data-stu-id="203ac-115">Select an event in the trace events window, or navigate through several adjacent rows in the trace events window by using the arrow keys.</span></span> <span data-ttu-id="203ac-116">La barra vertical roja de la ventana **Datos del Monitor de sistema** indica los datos del registro de rendimiento correlacionados con el evento de seguimiento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="203ac-116">The vertical red bar in the **System Monitor data** window indicates the performance log data that is correlated with the selected trace event.</span></span>  
  
6.  <span data-ttu-id="203ac-117">Haga clic en un punto de interés en el gráfico Monitor del sistema.</span><span class="sxs-lookup"><span data-stu-id="203ac-117">Click a point of interest in the System Monitor graph.</span></span> <span data-ttu-id="203ac-118">Se selecciona la fila correspondiente del seguimiento más cercana en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="203ac-118">The corresponding trace row that is nearest in time is selected.</span></span> <span data-ttu-id="203ac-119">Para ver más de cerca un intervalo de tiempo, presione el mouse (ratón) y arrastre el puntero en el gráfico Monitor del sistema.</span><span class="sxs-lookup"><span data-stu-id="203ac-119">To zoom in on a time range, press and drag the mouse pointer in the System Monitor graph.</span></span>  
  
### <a name="to-create-performance-logs-that-can-be-shared-among-different-versions-of-windows"></a><span data-ttu-id="203ac-120">Para crear registros de rendimiento que puedan compartirse entre diferentes versiones de Windows</span><span class="sxs-lookup"><span data-stu-id="203ac-120">To create performance logs that can be shared among different versions of Windows</span></span>  
  
1.  <span data-ttu-id="203ac-121">En el Panel de control, abra **Herramientas administrativas**y haga doble clic en **Rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="203ac-121">In Control Panel, open **Administrative Tools**, and then double click **Performance**.</span></span>  
  
2.  <span data-ttu-id="203ac-122">En el cuadro de diálogo **Rendimiento** , expanda **Registros y alertas de rendimiento**, haga clic con el botón derecho en **Registros de contador**y, después, haga clic en **Nueva configuración de registro**.</span><span class="sxs-lookup"><span data-stu-id="203ac-122">In the **Performance** dialog box, expand **Performance Logs and Alerts**, right-click **Counter Logs**, and then click **New Log Settings**.</span></span>  
  
3.  <span data-ttu-id="203ac-123">Escriba un nombre para el registro de contador y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="203ac-123">Type a name for the counter log, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="203ac-124">En la pestaña **General** , haga clic en **Agregar contadores**.</span><span class="sxs-lookup"><span data-stu-id="203ac-124">On the **General** tab, click **Add Counters**.</span></span>  
  
5.  <span data-ttu-id="203ac-125">En la lista **Objeto de rendimiento** , seleccione un objeto de rendimiento que desee supervisar.</span><span class="sxs-lookup"><span data-stu-id="203ac-125">In the **Performance object** list, select a performance object you want to monitor.</span></span> <span data-ttu-id="203ac-126">Los nombres de los objetos de rendimiento de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para instancias predeterminadas de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] comienzan con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y las instancias con nombre comienzan con MSSQL$*instanceName*.</span><span class="sxs-lookup"><span data-stu-id="203ac-126">The names of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] performance objects for default instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] start with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and named instances start with MSSQL$*instanceName*.</span></span>  
  
6.  <span data-ttu-id="203ac-127">Agregue tantos contadores como sean necesarios para la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y otros valores importantes, como el tiempo de procesador y el tiempo de disco.</span><span class="sxs-lookup"><span data-stu-id="203ac-127">Add as many counters as necessary for your [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance and other important values, such as processor time and disk time.</span></span>  
  
7.  <span data-ttu-id="203ac-128">Cuando haya terminado de agregar los contadores, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="203ac-128">When you have finished adding counters, click **Close**.</span></span>  
  
8.  <span data-ttu-id="203ac-129">Establezca los valores del intervalo **Tomar datos de muestra cada** .</span><span class="sxs-lookup"><span data-stu-id="203ac-129">Set values for the **Sample data every** interval.</span></span> <span data-ttu-id="203ac-130">Comience por un intervalo de muestreo moderado, como 5 minutos, y después ajuste el intervalo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="203ac-130">Start with a modest sampling interval, such as 5 minutes, and then adjust the interval if necessary.</span></span>  
  
9. <span data-ttu-id="203ac-131">En la pestaña **Archivos de registro** , elija **Archivo de texto (delimitado por comas)** en la lista **Tipo del archivo de registro** .</span><span class="sxs-lookup"><span data-stu-id="203ac-131">On the **Log Files** tab, choose **TextFile (Comma delimited)** from the **Log file type** list.</span></span> <span data-ttu-id="203ac-132">Los archivos de registro de texto delimitado por comas se pueden compartir entre diferentes versiones de Windows y se pueden ver más tarde en herramientas de elaboración de informes como Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="203ac-132">Comma-delimited text log files can be shared among different versions of Windows and can be viewed later in reporting tools such as Microsoft Excel.</span></span>  
  
10. <span data-ttu-id="203ac-133">En la pestaña **Programación** , especifique una programación de supervisión.</span><span class="sxs-lookup"><span data-stu-id="203ac-133">On the **Schedule** tab, specify a monitoring schedule.</span></span>  
  
11. <span data-ttu-id="203ac-134">Haga clic en **Aceptar** para crear el registro de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="203ac-134">Click **OK** to create the performance log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="203ac-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="203ac-135">See Also</span></span>  
 <span data-ttu-id="203ac-136">[Plantillas y permisos de SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="203ac-136">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="203ac-137">Iniciar SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="203ac-137">Start SQL Server Profiler</span></span>](../tools/sql-server-profiler/start-sql-server-profiler.md)  
  
  
