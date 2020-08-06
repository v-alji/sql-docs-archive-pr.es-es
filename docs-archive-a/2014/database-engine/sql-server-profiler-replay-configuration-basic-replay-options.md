---
title: Configuración de SQL Server Profiler-reproducción (opciones básicas de reproducción) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.generaloptions.f1
helpviewer_keywords:
- Replay Configuration dialog box
ms.assetid: 85a1dec6-9bbc-477a-86c5-b463db9ebb31
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cbf433c3108294909d91f7860136c0755b39b46f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748225"
---
# <a name="sql-server-profiler---replay-configuration-basic-replay-options"></a><span data-ttu-id="3302e-102">Analizador SQL Server (Configuración de reproducción/página Opciones básicas de reproducción)</span><span class="sxs-lookup"><span data-stu-id="3302e-102">SQL Server Profiler - Replay Configuration (Basic Replay Options)</span></span>
  <span data-ttu-id="3302e-103">En el cuadro de diálogo **Configuración de reproducción** , utilice la página **Opciones básicas de reproducción** para especificar cómo reproducir una tabla o un archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3302e-103">In the **Replay Configuration** dialog box, use the **Basic Replay Options** page to specify how to replay a trace file or table.</span></span>  
  
 <span data-ttu-id="3302e-104">Para ver esta ventana, utilice el [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] para abrir un seguimiento o un archivo de seguimiento que contenga los eventos adecuados para la reproducción.</span><span class="sxs-lookup"><span data-stu-id="3302e-104">To view this window, use [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to open a trace file or table that contains the appropriate events for replay.</span></span> <span data-ttu-id="3302e-105">Para más información, consulte [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3302e-105">For more information, see [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span></span> <span data-ttu-id="3302e-106">Cuando la tabla o el archivo de seguimiento están abiertos, en el menú **Reproducir** , haga clic en **Iniciar**y, a continuación, establezca la conexión con la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] donde desea reproducir el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3302e-106">While the trace file or table is open, on the **Replay** menu, click **Start**, and then connect to the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] where you want to replay the trace.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3302e-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="3302e-107">Options</span></span>  
 <span data-ttu-id="3302e-108">**Servidor de reproducción**</span><span class="sxs-lookup"><span data-stu-id="3302e-108">**Replay server**</span></span>  
 <span data-ttu-id="3302e-109">Muestra la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] con la que se establece la conexión para la reproducción.</span><span class="sxs-lookup"><span data-stu-id="3302e-109">Displays the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to connect to for the replay.</span></span>  
  
 <span data-ttu-id="3302e-110">**Cambiar...**</span><span class="sxs-lookup"><span data-stu-id="3302e-110">**Change...**</span></span>  
 <span data-ttu-id="3302e-111">Inicia el cuadro de diálogo **Conectar al servidor** para conectarse a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="3302e-111">Launches the **Connect to Server** dialog box to connect to another server.</span></span>  
  
 <span data-ttu-id="3302e-112">**Guardar en el archivo**</span><span class="sxs-lookup"><span data-stu-id="3302e-112">**Save to file**</span></span>  
 <span data-ttu-id="3302e-113">Guarda los resultados de la reproducción en un archivo.</span><span class="sxs-lookup"><span data-stu-id="3302e-113">Save the replay results to a file.</span></span> [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="3302e-114">muestra el cuadro de diálogo de archivo estándar, en el puede especificar la ubicación en la que se guarda el archivo.</span><span class="sxs-lookup"><span data-stu-id="3302e-114">displays the standard file dialog, where you can specify the location to save the file.</span></span>  
  
 <span data-ttu-id="3302e-115">**Guardar en la tabla**</span><span class="sxs-lookup"><span data-stu-id="3302e-115">**Save to table**</span></span>  
 <span data-ttu-id="3302e-116">Guarda los resultados de la reproducción en una tabla.</span><span class="sxs-lookup"><span data-stu-id="3302e-116">Save the replay results to a table.</span></span> [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="3302e-117">muestra el cuadro de diálogo de selección de tabla, en el puede especificar la ubicación en la que se guarda la tabla.</span><span class="sxs-lookup"><span data-stu-id="3302e-117">displays the table selection dialog, where you can specify the location to save the table.</span></span>  
  
 <span data-ttu-id="3302e-118">**Número de subprocesos de reproducción**</span><span class="sxs-lookup"><span data-stu-id="3302e-118">**Number of replay threads**</span></span>  
 <span data-ttu-id="3302e-119">Especifique el número de subprocesos de reproducción que se utilizarán simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="3302e-119">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="3302e-120">Un número mayor consume más recursos durante la reproducción, pero ésta es más rápida y simultánea.</span><span class="sxs-lookup"><span data-stu-id="3302e-120">A higher number consumes more resources during replay, but replay is faster and more concurrent.</span></span>  
  
 <span data-ttu-id="3302e-121">**Reproducir eventos en el orden del seguimiento**</span><span class="sxs-lookup"><span data-stu-id="3302e-121">**Replay events in the order they were traced**</span></span>  
 <span data-ttu-id="3302e-122">Reproduce los eventos de forma secuencial.</span><span class="sxs-lookup"><span data-stu-id="3302e-122">Replay events sequentially.</span></span> <span data-ttu-id="3302e-123">Utilice esta opción si reproduce un seguimiento para depuración.</span><span class="sxs-lookup"><span data-stu-id="3302e-123">Use this option if you are replaying a trace for debugging.</span></span>  
  
 <span data-ttu-id="3302e-124">**Reproducir eventos mediante múltiples subprocesos**</span><span class="sxs-lookup"><span data-stu-id="3302e-124">**Replay events using multiple threads**</span></span>  
 <span data-ttu-id="3302e-125">Reproduce los eventos de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="3302e-125">Replay events concurrently.</span></span> <span data-ttu-id="3302e-126">Esta opción es más rápida que la reproducción secuencial, pero deshabilita la depuración.</span><span class="sxs-lookup"><span data-stu-id="3302e-126">This option is faster than replaying events sequentially, but disables debugging.</span></span> <span data-ttu-id="3302e-127">Los eventos se ordenan dentro de sus identificadores de proceso del sistema (SPID).</span><span class="sxs-lookup"><span data-stu-id="3302e-127">The events are ordered within their system process identifiers (SPID).</span></span>  
  
 <span data-ttu-id="3302e-128">**Mostrar los resultados de la reproducción**</span><span class="sxs-lookup"><span data-stu-id="3302e-128">**Display replay results**</span></span>  
 <span data-ttu-id="3302e-129">Muestra el resultado de la reproducción en el [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3302e-129">Display replay results in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3302e-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3302e-130">See Also</span></span>  
 <span data-ttu-id="3302e-131">[Reproducir una tabla de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="3302e-131">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="3302e-132">[Reproducir un archivo de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="3302e-132">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="3302e-133">Reproducir seguimientos</span><span class="sxs-lookup"><span data-stu-id="3302e-133">Replay Traces</span></span>](../tools/sql-server-profiler/replay-traces.md)  
  
  
