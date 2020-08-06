---
title: SQL Server Profiler-Tools-Options (página Opciones generales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.tools.generaloptions.f1
helpviewer_keywords:
- General Options dialog box
ms.assetid: a888246d-ccfe-415f-bbdc-d6adafac250a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fad4d3529482835367898276a973bd7c8827b553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674979"
---
# <a name="sql-server-profiler---tools-options-general-options-page"></a><span data-ttu-id="0c083-102">SQL Server Profiler-herramientas-opciones (página Opciones generales)</span><span class="sxs-lookup"><span data-stu-id="0c083-102">SQL Server Profiler - Tools-Options (General Options Page)</span></span>
  <span data-ttu-id="0c083-103">Utilice el cuadro de diálogo **Opciones generales** para ver o especificar las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="0c083-103">Use the **General Options** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0c083-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="0c083-104">Options</span></span>  
  
### <a name="display-options"></a><span data-ttu-id="0c083-105">Opciones de visualización</span><span class="sxs-lookup"><span data-stu-id="0c083-105">Display Options</span></span>  
 <span data-ttu-id="0c083-106">**Nombre de fuente**</span><span class="sxs-lookup"><span data-stu-id="0c083-106">**Font name**</span></span>  
 <span data-ttu-id="0c083-107">Muestra el nombre de la fuente utilizada en la cuadrícula de resultados de seguimiento durante los seguimientos.</span><span class="sxs-lookup"><span data-stu-id="0c083-107">Displays the name of the font used in the trace results grid during traces.</span></span>  
  
 <span data-ttu-id="0c083-108">**Tamaño de fuente**</span><span class="sxs-lookup"><span data-stu-id="0c083-108">**Font size**</span></span>  
 <span data-ttu-id="0c083-109">Muestra el tamaño de la fuente utilizada en la cuadrícula de resultados de seguimiento durante los seguimientos.</span><span class="sxs-lookup"><span data-stu-id="0c083-109">Displays the size of the font used in the trace results grid during traces.</span></span>  
  
 <span data-ttu-id="0c083-110">**Elegir fuente**</span><span class="sxs-lookup"><span data-stu-id="0c083-110">**Choose Font**</span></span>  
 <span data-ttu-id="0c083-111">Abre un cuadro de diálogo para cambiar la configuración de fuente.</span><span class="sxs-lookup"><span data-stu-id="0c083-111">Opens a dialog to change the font settings.</span></span>  
  
 <span data-ttu-id="0c083-112">**Usar la configuración regional para mostrar valores de fecha y hora**</span><span class="sxs-lookup"><span data-stu-id="0c083-112">**Use regional settings to display date and time values**</span></span>  
 <span data-ttu-id="0c083-113">Muestra los valores de fecha y hora en la configuración regional establecida en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0c083-113">Displays date and time values in regional settings configured for your computer.</span></span> <span data-ttu-id="0c083-114">Si no selecciona esta opción, los valores de fecha y hora se muestran en el formato fijo que utiliza Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], que incluye milisegundos.</span><span class="sxs-lookup"><span data-stu-id="0c083-114">If you do not select this option, the date and time values are displayed in the fixed format used by Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], which includes milliseconds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c083-115">Si activa o desactiva esta casilla se cambia el formato de presentación de las columnas de hora como **Hora de inicio** y **Hora de finalización**.</span><span class="sxs-lookup"><span data-stu-id="0c083-115">Toggling this checkbox changes the time columns display format such as **StartTime** and **EndTime**.</span></span> <span data-ttu-id="0c083-116">Pero no cambia los parámetros del valor **DateTime** dentro de los eventos de lenguaje o las llamadas a procedimientos remotos (RPC).</span><span class="sxs-lookup"><span data-stu-id="0c083-116">However, it does not change the **DateTime** value parameters inside the language events or remote procedure calls (RPCs).</span></span>  
  
 <span data-ttu-id="0c083-117">**Mostrar valores en la columna Duración en microsegundos**</span><span class="sxs-lookup"><span data-stu-id="0c083-117">**Show values in Duration column in microseconds**</span></span>  
 <span data-ttu-id="0c083-118">Muestra los valores en microsegundos en la columna de datos **Duración** de los seguimientos.</span><span class="sxs-lookup"><span data-stu-id="0c083-118">Displays the values in microseconds in the **Duration** data column of traces.</span></span> <span data-ttu-id="0c083-119">De manera predeterminada, la columna **Duración** muestra los valores en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="0c083-119">By default, the **Duration** column displays values in milliseconds.</span></span>  
  
### <a name="tracing-options"></a><span data-ttu-id="0c083-120">Opciones de traza</span><span class="sxs-lookup"><span data-stu-id="0c083-120">Tracing Options</span></span>  
 <span data-ttu-id="0c083-121">**Iniciar la traza inmediatamente tras realizar la conexión**</span><span class="sxs-lookup"><span data-stu-id="0c083-121">**Start tracing immediately after making connection**</span></span>  
 <span data-ttu-id="0c083-122">Inicia un seguimiento con la plantilla predeterminada en cuanto se establece una conexión.</span><span class="sxs-lookup"><span data-stu-id="0c083-122">Begin a trace using the default template as soon as a connection is made.</span></span>  
  
 <span data-ttu-id="0c083-123">**Actualizar definición de seguimiento cuando cambie la versión del proveedor**</span><span class="sxs-lookup"><span data-stu-id="0c083-123">**Update trace definition when provider version changes**</span></span>  
 <span data-ttu-id="0c083-124">Aplica la definición de seguimiento más actual a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cuando se actualiza el proveedor.</span><span class="sxs-lookup"><span data-stu-id="0c083-124">Apply the most current trace definition to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] when the provider is updated.</span></span> <span data-ttu-id="0c083-125">Esta opción no está activada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0c083-125">This item is not checked by default.</span></span> <span data-ttu-id="0c083-126">Esto obliga a que el [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] consulte al servidor la definición de seguimiento y vuelva a crear, si existe, el archivo en el disco.</span><span class="sxs-lookup"><span data-stu-id="0c083-126">This forces [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to query the server for the trace definition and re-create, if one exists, the file on disk.</span></span>  
  
### <a name="file-rollover-options"></a><span data-ttu-id="0c083-127">Opciones de sustitución incremental de archivos</span><span class="sxs-lookup"><span data-stu-id="0c083-127">File Rollover Options</span></span>  
 <span data-ttu-id="0c083-128">**Cargar todos los archivos de sustitución incremental en secuencia sin preguntar**</span><span class="sxs-lookup"><span data-stu-id="0c083-128">**Load all rollover files in sequence without prompting**</span></span>  
 <span data-ttu-id="0c083-129">Carga automáticamente los archivos de sustitución incremental cuando se abre un archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0c083-129">Load rollover files automatically when a trace file is opened.</span></span> <span data-ttu-id="0c083-130">Si se ha creado más de un archivo durante la traza, la selección de esta opción carga automáticamente todos los archivos de sustitución incremental.</span><span class="sxs-lookup"><span data-stu-id="0c083-130">If more than one file was created while tracing, selecting this option automatically loads all rollover files.</span></span>  
  
 <span data-ttu-id="0c083-131">**Preguntar antes de cargar archivos de sustitución incremental**</span><span class="sxs-lookup"><span data-stu-id="0c083-131">**Prompt before loading rollover files**</span></span>  
 <span data-ttu-id="0c083-132">Cuando se abre un archivo de seguimiento, el [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] pregunta antes de agregar un archivo de sustitución incremental.</span><span class="sxs-lookup"><span data-stu-id="0c083-132">Have [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] prompt you before adding a rollover file when a trace file is opened.</span></span>  
  
 <span data-ttu-id="0c083-133">**No cargar nunca los archivos siguientes de sustitución incremental**</span><span class="sxs-lookup"><span data-stu-id="0c083-133">**Never load subsequent rollover files**</span></span>  
 [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="0c083-134">no carga archivos de sustitución incremental.</span><span class="sxs-lookup"><span data-stu-id="0c083-134">never loads subsequent rollover files when a trace file is opened.</span></span>  
  
### <a name="replay-options"></a><span data-ttu-id="0c083-135">Opciones de reproducción</span><span class="sxs-lookup"><span data-stu-id="0c083-135">Replay Options</span></span>  
 <span data-ttu-id="0c083-136">**Número predeterminado de subprocesos de reproducción**</span><span class="sxs-lookup"><span data-stu-id="0c083-136">**Default number of replay threads**</span></span>  
 <span data-ttu-id="0c083-137">Especifique el número de subprocesos de reproducción que se utilizarán simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="0c083-137">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="0c083-138">Un número más alto consume más recursos durante la reproducción, pero aumenta la simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="0c083-138">A higher number consumes more resources during replay, but increases replay concurrency.</span></span>  
  
 <span data-ttu-id="0c083-139">**Intervalo de espera del monitor de estado predeterminado (seg.)**</span><span class="sxs-lookup"><span data-stu-id="0c083-139">**Default health monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="0c083-140">Especifique el intervalo de espera de la reproducción en segundos.</span><span class="sxs-lookup"><span data-stu-id="0c083-140">Specify the wait interval to replay in seconds.</span></span> <span data-ttu-id="0c083-141">El valor predeterminado es 3600 segundos (1 hora).</span><span class="sxs-lookup"><span data-stu-id="0c083-141">Default is 3600 seconds (1 hour).</span></span> <span data-ttu-id="0c083-142">Esta configuración afecta al tiempo que puede ejecutarse un subproceso antes de que lo finalice el monitor de estado.</span><span class="sxs-lookup"><span data-stu-id="0c083-142">This setting affects the amount of time a thread is allowed to run before being terminated by the health monitor.</span></span>  
  
 <span data-ttu-id="0c083-143">**Intervalo de sondeo del monitor de estado predeterminado (seg.)**</span><span class="sxs-lookup"><span data-stu-id="0c083-143">**Default health monitor poll interval (sec)**</span></span>  
 <span data-ttu-id="0c083-144">Especifique el intervalo de sondeo del monitor de estado durante la reproducción en segundos.</span><span class="sxs-lookup"><span data-stu-id="0c083-144">Specify the health monitor poll interval during replay in seconds.</span></span> <span data-ttu-id="0c083-145">El valor predeterminado es 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="0c083-145">Default is 60 seconds.</span></span> <span data-ttu-id="0c083-146">Este valor permite al usuario configurar la frecuencia con que el monitor de estado sondea los candidatos para terminar.</span><span class="sxs-lookup"><span data-stu-id="0c083-146">This value allows the user to configure how often the health monitor polls for candidates for termination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c083-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c083-147">See Also</span></span>  
 <span data-ttu-id="0c083-148">[Iniciar un seguimiento automáticamente después de conectarse a un servidor &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="0c083-148">[Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="0c083-149">[Establecer valores predeterminados de presentación de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="0c083-149">[Set Trace Display Defaults &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="0c083-150">[Reproducir una tabla de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="0c083-150">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="0c083-151">[Reproducir un archivo de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="0c083-151">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="0c083-152">[Reproducir seguimientos](../tools/sql-server-profiler/replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="0c083-152">[Replay Traces](../tools/sql-server-profiler/replay-traces.md) </span></span>  
 <span data-ttu-id="0c083-153">[Establecer opciones globales de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="0c083-153">[Set Global Trace Options &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="0c083-154">[Plantillas y permisos de SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="0c083-154">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="0c083-155">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="0c083-155">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
