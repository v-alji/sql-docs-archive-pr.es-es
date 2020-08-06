---
title: Opciones de reproducción (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
- health monitor [SQL Server]
- Replay Configuration dialog box
ms.assetid: 58761a25-a84f-4a90-9c61-97700bc5ad9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 695a1431145813f0a7829626a380e510d0e602e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748410"
---
# <a name="replay-options-sql-server-profiler"></a><span data-ttu-id="541ba-102">Opciones de reproducción (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="541ba-102">Replay Options (SQL Server Profiler)</span></span>
  <span data-ttu-id="541ba-103">Antes de reproducir un seguimiento capturado con [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], puede reproducir las opciones en el cuadro de diálogo **Configuración de reproducción** .</span><span class="sxs-lookup"><span data-stu-id="541ba-103">Before replaying a captured trace with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], specify replay options in the **Replay Configuration** dialog box.</span></span> <span data-ttu-id="541ba-104">Para iniciar este cuadro de diálogo, abra el archivo o tabla de seguimiento en el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], y en el menú **Reproducir** , haga clic en **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="541ba-104">To launch this dialog box, open the replay trace file or table in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], and on the **Replay** menu, click **Start**.</span></span> <span data-ttu-id="541ba-105">Para obtener información acerca de los permisos necesarios para reproducir un seguimiento, vea [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="541ba-105">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
 <span data-ttu-id="541ba-106">En este tema se describen las opciones especificadas con el cuadro de diálogo **Configuración de reproducción** .</span><span class="sxs-lookup"><span data-stu-id="541ba-106">This topic describes the options specified with the **Replay Configuration** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="541ba-107">Recomendamos usar la Utilidad de reproducción distribuida para reproducir una aplicación de OLTP que se use mucho (con muchas conexiones simultáneas activas o un alto rendimiento).</span><span class="sxs-lookup"><span data-stu-id="541ba-107">We recommend using the Distributed Replay Utility for replaying an intensive OLTP application (with many active concurrent connections or high throughput).</span></span> <span data-ttu-id="541ba-108">La utilidad puede reproducir datos de seguimiento desde varios equipos, simulando mejor una carga de trabajo esencial.</span><span class="sxs-lookup"><span data-stu-id="541ba-108">The Distributed Replay Utility can replay trace data from multiple computers, better simulating a mission-critical workload.</span></span> <span data-ttu-id="541ba-109">Para obtener más información, vea [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="541ba-109">For more information, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
## <a name="basic-replay-options"></a><span data-ttu-id="541ba-110">Opciones básicas de reproducción</span><span class="sxs-lookup"><span data-stu-id="541ba-110">Basic Replay Options</span></span>  
 <span data-ttu-id="541ba-111">**Servidor de reproducción**</span><span class="sxs-lookup"><span data-stu-id="541ba-111">**Replay server**</span></span>  
 <span data-ttu-id="541ba-112">El servidor es el nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la que desea reproducir el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="541ba-112">The server is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] against which you want to replay the trace.</span></span> <span data-ttu-id="541ba-113">El servidor debe cumplir los requisitos de reproducción que se describen en [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="541ba-113">The server must adhere to the replay requirements described in [Replay Requirements](replay-requirements.md)."</span></span>  
  
 <span data-ttu-id="541ba-114">**Guardar en el archivo**</span><span class="sxs-lookup"><span data-stu-id="541ba-114">**Save to file**</span></span>  
 <span data-ttu-id="541ba-115">El archivo de salida en el que se escriben los resultados de la reproducción del seguimiento para verlos posteriormente.</span><span class="sxs-lookup"><span data-stu-id="541ba-115">The output file where the result of replaying the trace is written for later viewing.</span></span> <span data-ttu-id="541ba-116">De manera predeterminada, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] solo muestra en pantalla los resultados de la reproducción del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="541ba-116">By default, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] displays only the results of replaying the trace on the screen.</span></span>  
  
 <span data-ttu-id="541ba-117">**Guardar en la tabla**</span><span class="sxs-lookup"><span data-stu-id="541ba-117">**Save to table**</span></span>  
 <span data-ttu-id="541ba-118">La tabla de base de datos en la que se escriben los resultados de la reproducción del seguimiento para verlos posteriormente.</span><span class="sxs-lookup"><span data-stu-id="541ba-118">The database table where the result of replaying the trace is written for later viewing.</span></span>  
  
 <span data-ttu-id="541ba-119">**Número de subprocesos de reproducción**</span><span class="sxs-lookup"><span data-stu-id="541ba-119">**Number of replay threads**</span></span>  
 <span data-ttu-id="541ba-120">Especifique el número de subprocesos de reproducción que se utilizarán simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="541ba-120">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="541ba-121">Un número alto consume más recursos durante la reproducción, pero ésta es más rápida.</span><span class="sxs-lookup"><span data-stu-id="541ba-121">A higher number consumes more resources during replay, but replay is faster.</span></span> <span data-ttu-id="541ba-122">El orden de los eventos no se mantiene completamente cuando se utilizan varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="541ba-122">Event ordering is not fully maintained when multiple threads are used.</span></span>  
  
 <span data-ttu-id="541ba-123">**Reproducir eventos en el orden del seguimiento**</span><span class="sxs-lookup"><span data-stu-id="541ba-123">**Replay events in the order they were traced**</span></span>  
 <span data-ttu-id="541ba-124">Le permite utilizar métodos de depuración, como recorrer paso a paso cada seguimiento.</span><span class="sxs-lookup"><span data-stu-id="541ba-124">Allows you to use debugging methods such as stepping through each trace.</span></span> <span data-ttu-id="541ba-125">Si no se activa esta opción, la reproducción no garantiza que los eventos se reproduzcan en un orden coherente con el orden en el que se capturaron originalmente.</span><span class="sxs-lookup"><span data-stu-id="541ba-125">If this option is not selected, replay does not guarantee that events are replayed in an order that is consistent with the order in which events were originally captured.</span></span>  
  
 <span data-ttu-id="541ba-126">**Reproducir eventos mediante múltiples subprocesos**</span><span class="sxs-lookup"><span data-stu-id="541ba-126">**Replay events using multiple threads**</span></span>  
 <span data-ttu-id="541ba-127">Optimiza el rendimiento y deshabilita la depuración.</span><span class="sxs-lookup"><span data-stu-id="541ba-127">Optimizes performance and disables debugging.</span></span> <span data-ttu-id="541ba-128">Los eventos se reproducen en el orden en el que se registraron para un Id. de proceso de servidor (SPID) determinado, pero no se garantiza el orden de los SPID.</span><span class="sxs-lookup"><span data-stu-id="541ba-128">Events are replayed in the order they were recorded for a particular server process ID (SPID), but ordering of SPIDs is not guaranteed.</span></span>  
  
 <span data-ttu-id="541ba-129">**Mostrar los resultados de la reproducción**</span><span class="sxs-lookup"><span data-stu-id="541ba-129">**Display replay results**</span></span>  
 <span data-ttu-id="541ba-130">Muestra los resultados de la reproducción.</span><span class="sxs-lookup"><span data-stu-id="541ba-130">Display the results of the replay.</span></span> <span data-ttu-id="541ba-131">Ésta es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="541ba-131">This is the default option.</span></span> <span data-ttu-id="541ba-132">Si el seguimiento que está reproduciendo es muy grande, puede que le interese deshabilitar la opción para ahorrar espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="541ba-132">If the trace you are replaying is very large, you may want to disable this to save disk space.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="541ba-133">Para conseguir un rendimiento de reproducción óptimo, se recomienda seleccionar la opción de reproducir eventos con múltiples subprocesos y no seleccionar la opción de mostrar los resultados de la reproducción.</span><span class="sxs-lookup"><span data-stu-id="541ba-133">For best replay performance, we recommend that you select to replay events using multiple threads, and do not select to display the replay results.</span></span>  
  
## <a name="advanced-replay-options"></a><span data-ttu-id="541ba-134">Opciones avanzadas de reproducción</span><span class="sxs-lookup"><span data-stu-id="541ba-134">Advanced Replay Options</span></span>  
 <span data-ttu-id="541ba-135">**Reproducir los SPID del sistema**</span><span class="sxs-lookup"><span data-stu-id="541ba-135">**Replay system SPIDs**</span></span>  
 <span data-ttu-id="541ba-136">Reproduce los SPID del sistema</span><span class="sxs-lookup"><span data-stu-id="541ba-136">Replay all SPIDs.</span></span> <span data-ttu-id="541ba-137">Ésta es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="541ba-137">This is the default option.</span></span>  
  
 <span data-ttu-id="541ba-138">**Reproducir solo un SPID**</span><span class="sxs-lookup"><span data-stu-id="541ba-138">**Replay one SPID only**</span></span>  
 <span data-ttu-id="541ba-139">Reproduce el número de SPID que elija en la lista.</span><span class="sxs-lookup"><span data-stu-id="541ba-139">Replays the SPID number you choose from the list.</span></span>  
  
 <span data-ttu-id="541ba-140">**Limitar reproducción por fecha y hora**</span><span class="sxs-lookup"><span data-stu-id="541ba-140">**Limit replay by date and time**</span></span>  
 <span data-ttu-id="541ba-141">Reproduce el seguimiento para la **Hora de inicio** y la **Hora de finalización**especificadas.</span><span class="sxs-lookup"><span data-stu-id="541ba-141">Replays the trace for the specified **Start time** and **End time**.</span></span>  
  
 <span data-ttu-id="541ba-142">**Intervalo de espera del monitor de estado**</span><span class="sxs-lookup"><span data-stu-id="541ba-142">**Health monitor wait interval**</span></span>  
 <span data-ttu-id="541ba-143">Establece la cantidad de tiempo que se permite la ejecución de un proceso antes de que el monitor de estado lo finalice.</span><span class="sxs-lookup"><span data-stu-id="541ba-143">Sets the amount of time a process is allowed to run before the health monitor terminates it.</span></span>  
  
 <span data-ttu-id="541ba-144">**Intervalo de sondeo del monitor de estado**</span><span class="sxs-lookup"><span data-stu-id="541ba-144">**Health monitor poll interval**</span></span>  
 <span data-ttu-id="541ba-145">Establece la frecuencia con la que el monitor de estado sondea los procesos que puede tener que finalizar.</span><span class="sxs-lookup"><span data-stu-id="541ba-145">Sets how often the health monitor polls candidates for termination.</span></span>  
  
 <span data-ttu-id="541ba-146">**Habilitar monitor de procesos bloqueados de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="541ba-146">**Enable SQL Server blocked processes monitor**</span></span>  
 <span data-ttu-id="541ba-147">Establece la frecuencia con la que el monitor de procesos bloqueados busca procesos bloqueados o de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="541ba-147">Sets how often the blocked processes monitor searches for blocked or blocking processes.</span></span>  
  
## <a name="about-the-health-monitor"></a><span data-ttu-id="541ba-148">Acerca del monitor de estado</span><span class="sxs-lookup"><span data-stu-id="541ba-148">About the Health Monitor</span></span>  
 <span data-ttu-id="541ba-149">El monitor de estado es un subproceso de aplicación que supervisa los procesos simulados que participan en la reproducción de un seguimiento y finaliza los procesos que están bloqueados en la reproducción.</span><span class="sxs-lookup"><span data-stu-id="541ba-149">The health monitor is an application thread that monitors the simulated processes involved in replaying a trace, and ends those processes that are blocked within the replay.</span></span> <span data-ttu-id="541ba-150">En la pestaña **Opciones avanzadas de reproducción** del cuadro de diálogo **Configuración de reproducción** , puede especificar cuánto tiempo en segundos debe esperar el monitor de mantenimiento antes de finalizar un proceso bloqueado (**Intervalo de espera del monitor de mantenimiento**).</span><span class="sxs-lookup"><span data-stu-id="541ba-150">In the **Advanced Replay Options** tab of the **Replay Configuration** dialog box, you can specify how long the health monitor should wait in seconds before ending a blocked process (**Health monitor wait interval**).</span></span> <span data-ttu-id="541ba-151">Si el intervalo se configura en 0, el monitor de estado nunca finaliza los procesos de bloqueo simulados en el seguimiento de reproducción.</span><span class="sxs-lookup"><span data-stu-id="541ba-151">If you set this interval to 0, the health monitor never ends simulated blocking processes in the replaying trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="541ba-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="541ba-152">See Also</span></span>  
 <span data-ttu-id="541ba-153">[Reproducir seguimientos](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="541ba-153">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="541ba-154">[Requisitos de reproducción](replay-requirements.md) </span><span class="sxs-lookup"><span data-stu-id="541ba-154">[Replay Requirements](replay-requirements.md) </span></span>  
 [<span data-ttu-id="541ba-155">Consideraciones para reproducir seguimientos &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="541ba-155">Considerations for Replaying Traces &#40;SQL Server Profiler&#41;</span></span>](considerations-for-replaying-traces-sql-server-profiler.md)  
  
  
