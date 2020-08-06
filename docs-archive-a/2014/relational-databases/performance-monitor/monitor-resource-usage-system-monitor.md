---
title: Supervisión del uso de recursos (Monitor de sistema) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server], resource usage
- System Monitor [SQL Server], about Windows System Monitor
- resource usage monitoring [SQL Server]
- System Monitor [SQL Server]
- counters [SQL Server], resource usage subjects
- performance counters [SQL Server], resource usage subjects
- Windows System Monitor [SQL Server], about Windows System Monitor
- monitoring [SQL Server], server resource usage
- monitoring resource usage [SQL Server]
- Windows System Monitor [SQL Server]
- database monitoring [SQL Server], resource usage
- database performance [SQL Server], resource usage
- tuning databases [SQL Server], resource usage
- server performance [SQL Server], resource usage
ms.assetid: f2993a28-0b81-46f2-aec0-6877fe990387
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d691091a41e3161c733902824bf439b6788cc4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677038"
---
# <a name="monitor-resource-usage-system-monitor"></a><span data-ttu-id="cbf4a-102">Supervisar el uso de recursos (Monitor de sistema)</span><span class="sxs-lookup"><span data-stu-id="cbf4a-102">Monitor Resource Usage (System Monitor)</span></span>
  <span data-ttu-id="cbf4a-103">Si está ejecutando el sistema operativo de servidor de Microsoft Windows, utilice la herramienta gráfica Monitor de sistema para medir el rendimiento de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbf4a-103">If you are running Microsoft Windows server operating system, use the System Monitor graphical tool to measure the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cbf4a-104">Puede ver los objetos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , los contadores de rendimiento y el comportamiento de otros objetos, como procesadores, memoria, caché, subprocesos y procesos.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-104">You can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects, performance counters, and the behavior of other objects, such as processors, memory, cache, threads, and processes.</span></span> <span data-ttu-id="cbf4a-105">Cada uno de estos objetos tiene asociado un conjunto de contadores que miden el uso de los dispositivos, la longitud de las colas, las demoras y otros indicadores del rendimiento y la congestión interna.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-105">Each of these objects has an associated set of counters that measure device usage, queue lengths, delays, and other indicators of throughput and internal congestion.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cbf4a-106">El Monitor de sistema ha reemplazado al Monitor de rendimiento después de Windows NT 4.0.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-106">System Monitor replaced Performance Monitor after Windows NT 4.0.</span></span>  
  
## <a name="benefits-of-system-monitor"></a><span data-ttu-id="cbf4a-107">Ventajas del Monitor de sistema</span><span class="sxs-lookup"><span data-stu-id="cbf4a-107">Benefits of System Monitor</span></span>  
 <span data-ttu-id="cbf4a-108">El Monitor de sistema puede resultar útil para supervisar el sistema operativo Windows y los contadores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] al mismo tiempo con el fin de determinar las posibles correlaciones entre el rendimiento de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el de Windows.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-108">System Monitor can be useful to monitor Windows operating system and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] counters at the same time to determine any correlation between the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows.</span></span> <span data-ttu-id="cbf4a-109">Por ejemplo, la supervisión simultánea de los contadores de E/S de disco de Windows y los contadores del Administrador de búfer de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede mostrar el comportamiento del sistema en su totalidad.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-109">For example, monitoring the Windows disk input/output (I/O) counters and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Buffer Manager counters at the same time can reveal the behavior of the entire system.</span></span>  
  
 <span data-ttu-id="cbf4a-110">El Monitor de sistema permite obtener estadísticas sobre la actividad y el rendimiento actuales de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbf4a-110">System Monitor allows you to obtain statistics on current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] activity and performance.</span></span> <span data-ttu-id="cbf4a-111">Con el Monitor de sistema, puede:</span><span class="sxs-lookup"><span data-stu-id="cbf4a-111">Using System Monitor, you can:</span></span>  
  
-   <span data-ttu-id="cbf4a-112">Ver simultáneamente datos de cualquier número de equipos.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-112">View data simultaneously from any number of computers.</span></span>  
  
-   <span data-ttu-id="cbf4a-113">Ver y cambiar gráficos para reflejar la actividad actual y mostrar valores de contadores que se actualizan con la frecuencia definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-113">View and change charts to reflect current activity, and show counter values that are updated at a frequency that the user defines.</span></span>  
  
-   <span data-ttu-id="cbf4a-114">Exportar datos desde gráficos, registros, registros de alertas e informes a aplicaciones de hoja de cálculo o de base de datos para manipularlos e imprimirlos.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-114">Export data from charts, logs, alert logs, and reports to spreadsheet or database applications for further manipulation and printing.</span></span>  
  
-   <span data-ttu-id="cbf4a-115">Agregar alertas del sistema que muestran un evento en el registro de alertas y que pueden notificarse mediante una alerta de red.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-115">Add system alerts that list an event in the alert log and can notify you by issuing a network alert.</span></span>  
  
-   <span data-ttu-id="cbf4a-116">Ejecutar un programa predefinido la primera vez, o todas las veces, que el valor de un contador sea superior o inferior a un valor definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-116">Run a predefined application the first time or every time a counter value goes over or under a user-defined value.</span></span>  
  
-   <span data-ttu-id="cbf4a-117">Crear archivos de registro que contengan datos relativos a diversos objetos de equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-117">Create log files that contain data about various objects from different computers.</span></span>  
  
-   <span data-ttu-id="cbf4a-118">Anexar a un archivo secciones seleccionadas de otros archivos de registro existentes para crear un archivo de almacenamiento a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-118">Append to one file selected sections from other existing log files to form a long-term archive.</span></span>  
  
-   <span data-ttu-id="cbf4a-119">Ver informes de la actividad actual o crear informes a partir de archivos de registro existentes.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-119">View current-activity reports, or create reports from existing log files.</span></span>  
  
-   <span data-ttu-id="cbf4a-120">Guardar la configuración de gráficos, alertas, registros o informes individuales, o bien de toda el área de trabajo, para volverla a utilizar.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-120">Save individual chart, alert, log, or report settings, or the entire workspace setup for reuse.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbf4a-121">El Monitor de sistema ha reemplazado al Monitor de rendimiento después de Windows NT 4.0.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-121">System Monitor replaced the Performance Monitor after Windows NT 4.0.</span></span> <span data-ttu-id="cbf4a-122">Para realizar estas tareas, puede utilizar el Monitor de sistema o el Monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-122">You can use either the System Monitor or Performance Monitor to do these tasks.</span></span>  
  
## <a name="system-monitor-performance"></a><span data-ttu-id="cbf4a-123">Rendimiento del Monitor de sistema</span><span class="sxs-lookup"><span data-stu-id="cbf4a-123">System Monitor Performance</span></span>  
 <span data-ttu-id="cbf4a-124">Al supervisar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el sistema operativo Microsoft Windows para investigar problemas relacionados con el rendimiento, hay tres áreas principales en las que debe concentrarse inicialmente:</span><span class="sxs-lookup"><span data-stu-id="cbf4a-124">When you monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the Microsoft Windows operating system to investigate performance-related issues, concentrate your initial efforts in three main areas:</span></span>  
  
-   <span data-ttu-id="cbf4a-125">Actividad del disco</span><span class="sxs-lookup"><span data-stu-id="cbf4a-125">Disk activity</span></span>  
  
-   <span data-ttu-id="cbf4a-126">Utilización del procesador</span><span class="sxs-lookup"><span data-stu-id="cbf4a-126">Processor utilization</span></span>  
  
-   <span data-ttu-id="cbf4a-127">Uso de la memoria</span><span class="sxs-lookup"><span data-stu-id="cbf4a-127">Memory usage</span></span>  
  
 <span data-ttu-id="cbf4a-128">La supervisión de un equipo en el que se ejecuta el Monitor de sistema puede afectar un poco al rendimiento del equipo.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-128">Monitoring a computer on which System Monitor is running can affect computer performance slightly.</span></span> <span data-ttu-id="cbf4a-129">Por tanto, registre los datos del Monitor de sistema en otro disco o en otro equipo para reducir así el efecto en el equipo que está supervisando, o bien ejecute el Monitor de sistema desde un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-129">Therefore, either log the System Monitor data to another disk (or computer) so that it reduces the effect on the computer being monitored, or run System Monitor from a remote computer.</span></span> <span data-ttu-id="cbf4a-130">Supervise solo los contadores en los que esté interesado.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-130">Monitor only the counters in which you are interested.</span></span> <span data-ttu-id="cbf4a-131">Si supervisa demasiados contadores, la sobrecarga de uso de los recursos se agrega al proceso de supervisión y afecta al rendimiento del equipo que se está supervisando.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-131">If you monitor too many counters, resource usage overhead is added to the monitoring process and affects the performance of the computer that is being monitored.</span></span>  
  
## <a name="system-monitor-tasks"></a><span data-ttu-id="cbf4a-132">Tareas del Monitor de sistema</span><span class="sxs-lookup"><span data-stu-id="cbf4a-132">System Monitor Tasks</span></span>  
  
|<span data-ttu-id="cbf4a-133">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="cbf4a-133">Task Description</span></span>|<span data-ttu-id="cbf4a-134">Tema</span><span class="sxs-lookup"><span data-stu-id="cbf4a-134">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="cbf4a-135">Describe cuándo debe usarse el Monitor de sistema y explica la sobrecarga de rendimiento derivada del uso del Monitor de sistema.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-135">Describes when to use System Monitor and discusses performance overhead when you use System Monitor.</span></span>|[<span data-ttu-id="cbf4a-136">Ejecutar Monitor de sistema</span><span class="sxs-lookup"><span data-stu-id="cbf4a-136">Run System Monitor</span></span>](run-system-monitor.md)|  
|<span data-ttu-id="cbf4a-137">Describe cómo deben supervisarse los contadores de disco para determinar la actividad del disco y la cantidad de actividad de E/S que generan los componentes de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-137">Describes how to monitor disk counters to determine disk activity and the amount of I/O generated by their SQL Server components.</span></span>|[<span data-ttu-id="cbf4a-138">Supervisar el uso del disco</span><span class="sxs-lookup"><span data-stu-id="cbf4a-138">Monitor Disk Usage</span></span>](monitor-disk-usage.md)|  
|<span data-ttu-id="cbf4a-139">Describe cómo se supervisa una instancia de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para determinar si los índices de uso de la CPU son normales.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-139">Describes how to monitor an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to determine whether CPU usage rates are within normal ranges.</span></span>|[<span data-ttu-id="cbf4a-140">Supervisar el uso de la CPU</span><span class="sxs-lookup"><span data-stu-id="cbf4a-140">Monitor CPU Usage</span></span>](monitor-cpu-usage.md)|  
|<span data-ttu-id="cbf4a-141">Describe cómo se supervisa una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para confirmar que el uso de la memoria se encuentra dentro de los rangos normales.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-141">Describes how to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to confirm that memory usage is within typical ranges.</span></span>|[<span data-ttu-id="cbf4a-142">Supervisar el uso de la memoria</span><span class="sxs-lookup"><span data-stu-id="cbf4a-142">Monitor Memory Usage</span></span>](monitor-memory-usage.md)|  
|<span data-ttu-id="cbf4a-143">Describe cómo se crea una alerta que se activará cuando se alcance un valor de umbral en un contador del Monitor del sistema.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-143">Describes how to create an alert that is raised when a threshold value for a System Monitor counter has been reached.</span></span>|[<span data-ttu-id="cbf4a-144">Crear una alerta de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="cbf4a-144">Create a SQL Server Database Alert</span></span>](create-a-sql-server-database-alert.md)|  
|<span data-ttu-id="cbf4a-145">Describe cómo se crean gráficos, alertas, registros e informes para supervisar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbf4a-145">Describes how to you create charts, alerts, logs, and reports to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|[<span data-ttu-id="cbf4a-146">Crear gráficos, alertas, registros e informes</span><span class="sxs-lookup"><span data-stu-id="cbf4a-146">Create Charts, Alerts, Logs, and Reports</span></span>](create-charts-alerts-logs-and-reports.md)|  
|<span data-ttu-id="cbf4a-147">Muestra los objetos y contadores que el Monitor del sistema usa para supervisar la actividad de los equipos en los que se ejecuta una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbf4a-147">Lists objects and counters that System Monitor uses to monitor activity in computers running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|[<span data-ttu-id="cbf4a-148">Usar objetos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="cbf4a-148">Use SQL Server Objects</span></span>](use-sql-server-objects.md)|  
|<span data-ttu-id="cbf4a-149">Muestra los objetos y contadores que el Monitor del sistema usa para supervisar la actividad de OLTP en memoria.</span><span class="sxs-lookup"><span data-stu-id="cbf4a-149">Lists objects and counters that System Monitor uses to monitor In-Memory OLTP activity.</span></span>|[<span data-ttu-id="cbf4a-150">Contadores de rendimiento de OLTP &#40;en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="cbf4a-150">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)|  
  
  
