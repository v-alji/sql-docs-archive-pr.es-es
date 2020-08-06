---
title: Supervisión de la actividad y rendimiento del servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- activity monitoring [SQL Server]
- traces [SQL Server], how-to topics
- monitoring server performance [SQL Server], activity monitoring
- stored procedures [SQL Server], traces
- performance [SQL Server], servers
- servers [SQL Server], performance
- SQL Server Profiler, how-to topics
- SQL Server Management Studio [SQL Server], monitoring system
- Profiler [SQL Server Profiler], how-to topics
ms.assetid: f9abe48d-d6e9-4c38-a355-fc5eb5a95a25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a0fa7902d68c587a7733f07ceb8daccd3a6a98fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677601"
---
# <a name="server-performance-and-activity-monitoring"></a><span data-ttu-id="18f5e-102">Supervisión de la actividad y rendimiento del servidor</span><span class="sxs-lookup"><span data-stu-id="18f5e-102">Server Performance and Activity Monitoring</span></span>
  <span data-ttu-id="18f5e-103">El objetivo de supervisar bases de datos es evaluar el rendimiento de un servidor.</span><span class="sxs-lookup"><span data-stu-id="18f5e-103">The goal of monitoring databases is to assess how a server is performing.</span></span> <span data-ttu-id="18f5e-104">Una supervisión eficaz implica tomar instantáneas periódicas del rendimiento actual para aislar procesos que causan problemas y recopilar datos de forma continua a lo largo del tiempo para realizar el seguimiento de las tendencias de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="18f5e-104">Effective monitoring involves taking periodic snapshots of current performance to isolate processes that are causing problems, and gathering data continuously over time to track performance trends.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="18f5e-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el sistema operativo [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows proporcionan utilidades que permiten ver la condición actual de la base de datos y realizar un seguimiento del rendimiento a medida que las condiciones cambian.</span><span class="sxs-lookup"><span data-stu-id="18f5e-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows operating system provide utilities that let you view the current condition of the database and to track performance as conditions change.</span></span>  
  
 <span data-ttu-id="18f5e-106">La sección siguiente contiene temas que describen cómo utilizar las herramientas de supervisión de la actividad y el rendimiento de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y Windows.</span><span class="sxs-lookup"><span data-stu-id="18f5e-106">The following section contains topics that describe how to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows performance and activity monitoring tools.</span></span> <span data-ttu-id="18f5e-107">Incluye los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="18f5e-107">It contains the following topics:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18f5e-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="18f5e-108">In This Section</span></span>  
 <span data-ttu-id="18f5e-109">**Para realizar tareas de supervisión con herramientas de Windows**</span><span class="sxs-lookup"><span data-stu-id="18f5e-109">**To perform monitoring tasks with Windows tools**</span></span>  
  
-   [<span data-ttu-id="18f5e-110">Iniciar el Monitor de sistema &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-110">Start System Monitor &#40;Windows&#41;</span></span>](start-system-monitor-windows.md)  
  
-   [<span data-ttu-id="18f5e-111">Ver el registro de aplicación de Windows &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-111">View the Windows Application Log &#40;Windows&#41;</span></span>](view-the-windows-application-log-windows-10.md)  
  
 <span data-ttu-id="18f5e-112">**Para crear alertas de bases de datos de SQL Server con herramientas de Windows**</span><span class="sxs-lookup"><span data-stu-id="18f5e-112">**To create SQL Server database alerts with Windows tools**</span></span>  
  
-   [<span data-ttu-id="18f5e-113">Configurar una alerta de base de datos de SQL Server &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-113">Set Up a SQL Server Database Alert &#40;Windows&#41;</span></span>](set-up-a-sql-server-database-alert-windows.md)  
  
 <span data-ttu-id="18f5e-114">**Para realizar tareas de supervisión con SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="18f5e-114">**To perform monitoring tasks with SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="18f5e-115">Ver el registro de errores de SQL Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-115">View the SQL Server Error Log &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="18f5e-116">Abrir el Monitor de actividad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-116">Open Activity Monitor &#40;SQL Server Management Studio&#41;</span></span>](../performance-monitor/open-activity-monitor-sql-server-management-studio.md)  
  
 <span data-ttu-id="18f5e-117">**Para realizar tareas de supervisión con Seguimiento de SQL mediante procedimientos almacenados de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="18f5e-117">**To perform monitoring tasks with SQL Trace by using Transact-SQL stored procedures**</span></span>  
  
-   [<span data-ttu-id="18f5e-118">Crear un seguimiento &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-118">Create a Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/create-a-trace-transact-sql.md)  
  
-   [<span data-ttu-id="18f5e-119">Establecer un filtro de seguimiento &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-119">Set a Trace Filter &#40;Transact-SQL&#41;</span></span>](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md)  
  
-   [<span data-ttu-id="18f5e-120">Modificar un seguimiento existente &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-120">Modify an Existing Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/modify-an-existing-trace-transact-sql.md)  
  
-   [<span data-ttu-id="18f5e-121">Ver un seguimiento guardado &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-121">View a Saved Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/view-a-saved-trace-transact-sql.md)  
  
-   [<span data-ttu-id="18f5e-122">Ver la información del filtro &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-122">View Filter Information &#40;Transact-SQL&#41;</span></span>](../sql-trace/view-filter-information-transact-sql.md)  
  
-   [<span data-ttu-id="18f5e-123">Eliminar un seguimiento &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-123">Delete a Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/delete-a-trace-transact-sql.md)  
  
 <span data-ttu-id="18f5e-124">**Para crear y modificar seguimientos mediante SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="18f5e-124">**To create and modify traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="18f5e-125">Crear un seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-125">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-126">Establecer opciones globales de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-126">Set Global Trace Options &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-127">Especificar eventos y columnas de datos para un archivo de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-127">Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-128">Crear un script de Transact-SQL para ejecutar un seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-128">Create a Transact-SQL Script for Running a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-transact-sql-script-for-running-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-129">Guardar los resultados de un seguimiento en un archivo &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-129">Save Trace Results to a File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-130">Establecer un tamaño máximo de archivo para un archivo de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-130">Set a Maximum File Size for a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-a-maximum-file-size-for-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-131">Guardar los resultados de un seguimiento en una tabla &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-131">Save Trace Results to a Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-132">Establecer un tamaño máximo de tabla para una tabla de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-132">Set a Maximum Table Size for a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-a-maximum-table-size-for-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-133">Filtrar eventos en un seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-133">Filter Events in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-134">Ver información de un filtro &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-134">View Filter Information &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-135">Modificar un filtro &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-135">Modify a Filter &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-136">Filtrar eventos basándose en la hora de inicio del evento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-136">Filter Events Based on the Event Start Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-start-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-137">Filtrar eventos basándose en la hora de finalización del evento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-137">Filter Events Based on the Event End Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-end-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-138">Filtrar los Id. de proceso de servidor &#40;SPID&#41; en un seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-138">Filter Server Process IDs &#40;SPIDs&#41; in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-server-process-ids-spids-in-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-139">Organizar las columnas mostradas en un seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-139">Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md)  
  
 <span data-ttu-id="18f5e-140">**Para iniciar, pausar y detener seguimientos mediante SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="18f5e-140">**To start, pause, and stop traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="18f5e-141">Iniciar un seguimiento automáticamente después de conectarse a un servidor &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-141">Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-142">Pausar un seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-142">Pause a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/pause-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-143">Detener un seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-143">Stop a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/stop-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-144">Ejecutar un seguimiento después de haberlo pausado o detenido &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-144">Run a Trace After It Has Been Paused or Stopped &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/run-a-trace-after-it-has-been-paused-or-stopped-sql-server-profiler.md)  
  
 <span data-ttu-id="18f5e-145">**Para abrir seguimientos y configurar cómo se visualizan los seguimientos mediante SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="18f5e-145">**To open traces and configure how traces are displayed by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="18f5e-146">Abrir un archivo de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-146">Open a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-147">Abrir una tabla de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-147">Open a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-148">Borrar el contenido de una ventana de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-148">Clear a Trace Window &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/clear-a-trace-window-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-149">Cerrar una ventana de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-149">Close a Trace Window &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/close-a-trace-window-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-150">Configurar los valores predeterminados de definición de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-150">Set Trace Definition Defaults &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-trace-definition-defaults-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-151">Establecer los valores predeterminados de presentación de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-151">Set Trace Display Defaults &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md)  
  
 <span data-ttu-id="18f5e-152">**Para reproducir seguimientos mediante SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="18f5e-152">**To replay traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="18f5e-153">Reproducir un archivo de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-153">Replay a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-154">Reproducir una tabla de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-154">Replay a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-155">Reproducir un único evento cada vez &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-155">Replay a Single Event at a Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-single-event-at-a-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-156">Reproducir hasta un punto de interrupción &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-156">Replay to a Breakpoint &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-to-a-breakpoint-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-157">Reproducir hasta un cursor &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-157">Replay to a Cursor &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-to-a-cursor-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-158">Reproducir un script Transact-SQL &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-158">Replay a Transact-SQL Script &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-transact-sql-script-sql-server-profiler.md)  
  
 <span data-ttu-id="18f5e-159">**Para crear, modificar y utilizar plantillas de seguimientos mediante SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="18f5e-159">**To create, modify, and use trace templates by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="18f5e-160">Crear una plantilla de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-160">Create a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-161">Modificar una plantilla de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-161">Modify a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/modify-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-162">Derivar una plantilla a partir de un seguimiento en ejecución &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-162">Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-163">Derivar una plantilla a partir de un archivo o tabla de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-163">Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-164">Exportar una plantilla de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-164">Export a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/export-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-165">Importar una plantilla de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-165">Import a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/import-a-trace-template-sql-server-profiler.md)  
  
 <span data-ttu-id="18f5e-166">**Para utilizar seguimientos de SQL Server Profiler para recopilar y supervisar el rendimiento del servidor**</span><span class="sxs-lookup"><span data-stu-id="18f5e-166">**To use SQL Server Profiler traces to collect and monitor server performance**</span></span>  
  
-   [<span data-ttu-id="18f5e-167">Buscar un valor o una columna de datos durante la ejecución de un seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-167">Find a Value or Data Column While Tracing &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-168">Guardar gráficos de interbloqueo &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-168">Save Deadlock Graphs &#40;SQL Server Profiler&#41;</span></span>](save-deadlock-graphs-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-169">Guardar eventos Showplan XML por separado &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-169">Save Showplan XML Events Separately &#40;SQL Server Profiler&#41;</span></span>](save-showplan-xml-events-separately-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-170">Guardar de forma separada eventos Showplan XML Statistics Profile &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-170">Save Showplan XML Statistics Profile Events Separately &#40;SQL Server Profiler&#41;</span></span>](save-showplan-xml-statistics-profile-events-separately-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-171">Extraer un script de un seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-171">Extract a Script from a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/extract-a-script-from-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="18f5e-172">Establecer correlaciones de un seguimiento con datos del registro de rendimiento de Windows &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="18f5e-172">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/correlate-a-trace-with-windows-performance-log-data-sql-server-profiler.md)  
  
  
