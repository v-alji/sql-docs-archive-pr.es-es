---
title: Reproducir una tabla de seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 6a0ad817-3d8d-4495-889d-c66a7ef9e8bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: f3c26858fa852686bc3d9ccf4a26d47e04852647
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746651"
---
# <a name="replay-a-trace-table-sql-server-profiler"></a><span data-ttu-id="81b1b-102">Reproducir una tabla de seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="81b1b-102">Replay a Trace Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="81b1b-103">La reproducción es la capacidad de abrir un seguimiento guardado y reproducirlo más tarde.</span><span class="sxs-lookup"><span data-stu-id="81b1b-103">Replay is the ability to open a saved trace and replay it again.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="81b1b-104">incluye un motor de reproducción de varios subprocesos que puede simular conexiones de usuario y la Autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81b1b-104">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="81b1b-105">La reproducción es útil para solucionar problemas de aplicaciones o procesos.</span><span class="sxs-lookup"><span data-stu-id="81b1b-105">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="81b1b-106">Cuando identifique el problema e implemente las acciones para corregirlo, ejecute el seguimiento que encontró el posible problema en la aplicación o proceso corregido.</span><span class="sxs-lookup"><span data-stu-id="81b1b-106">When you identify the problem and implement corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="81b1b-107">A continuación, reproduzca el seguimiento original y compare los resultados.</span><span class="sxs-lookup"><span data-stu-id="81b1b-107">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="81b1b-108">Además de otras clases de eventos que desee supervisar, debe capturar clases de eventos específicas para habilitar la reproducción:</span><span class="sxs-lookup"><span data-stu-id="81b1b-108">In addition to any other event classes you want to monitor, specific event classes must be captured to enable replay.</span></span> <span data-ttu-id="81b1b-109">Estos eventos se capturan de forma predeterminada si se usa la plantilla de seguimiento **TSQL_Replay** .</span><span class="sxs-lookup"><span data-stu-id="81b1b-109">These events are captured by default if you use the **TSQL_Replay** trace template.</span></span> <span data-ttu-id="81b1b-110">Para más información, consulte [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81b1b-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
### <a name="to-replay-a-trace-table"></a><span data-ttu-id="81b1b-111">Para reproducir una tabla de seguimiento</span><span class="sxs-lookup"><span data-stu-id="81b1b-111">To replay a trace table</span></span>  
  
1.  <span data-ttu-id="81b1b-112">Abra una tabla de seguimiento que contenga las clases de eventos necesarias para la reproducción.</span><span class="sxs-lookup"><span data-stu-id="81b1b-112">Open a trace table that contains the event classes necessary for replay.</span></span>  
  
2.  <span data-ttu-id="81b1b-113">En el menú **Reproducir** , haga clic en **Iniciar**y conéctese a la instancia del servidor en la que desee reproducir el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="81b1b-113">On the **Replay** menu, click **Start**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="81b1b-114">En el cuadro de diálogo **Configuración de reproducción** , en la pestaña **Opciones básicas de reproducción** , especifique **Servidor de reproducción**.</span><span class="sxs-lookup"><span data-stu-id="81b1b-114">In the **Replay Configuration** dialog box, on the **Basic Replay Options** tab, specify **Replay server**.</span></span> <span data-ttu-id="81b1b-115">Haga clic en **Cambiar** para cambiar el servidor que aparece en el cuadro **Servidor de reproducción** .</span><span class="sxs-lookup"><span data-stu-id="81b1b-115">Click **Change** to change the server that is displayed in the **Replay server** box.</span></span>  
  
4.  <span data-ttu-id="81b1b-116">Opcionalmente, seleccione uno de los siguientes destinos para guardar la reproducción:</span><span class="sxs-lookup"><span data-stu-id="81b1b-116">Optionally, select one of the following destinations in which to save the replay:</span></span>  
  
    -   <span data-ttu-id="81b1b-117">**Guardar en el archivo,** que especifica un archivo en el que se guardará la reproducción.</span><span class="sxs-lookup"><span data-stu-id="81b1b-117">**Save to file,** which specifies a file in which to save the replay.</span></span>  
  
    -   <span data-ttu-id="81b1b-118">**Guardar en la tabla**, que especifica una tabla de base de datos en la que se guardará la reproducción.</span><span class="sxs-lookup"><span data-stu-id="81b1b-118">**Save to table**, which specifies a database table in which to save the replay.</span></span>  
  
5.  <span data-ttu-id="81b1b-119">Elija **Reproducir eventos en el oden de seguimiento**o **Reproducir eventos mediante múltiples subprocesos**.</span><span class="sxs-lookup"><span data-stu-id="81b1b-119">Choose either **Replay the events in the order they were traced**or **Replay events using multiple threads**.</span></span> <span data-ttu-id="81b1b-120">En la tabla siguiente se explica la diferencia entre estas opciones.</span><span class="sxs-lookup"><span data-stu-id="81b1b-120">The following table explains the difference between these settings.</span></span>  
  
    |<span data-ttu-id="81b1b-121">Opción</span><span class="sxs-lookup"><span data-stu-id="81b1b-121">Option</span></span>|<span data-ttu-id="81b1b-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="81b1b-122">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="81b1b-123">**Reproducir eventos en el orden del seguimiento**</span><span class="sxs-lookup"><span data-stu-id="81b1b-123">**Replay events in the order they were traced**</span></span>|<span data-ttu-id="81b1b-124">Reproduce los eventos en el orden en que se registraron.</span><span class="sxs-lookup"><span data-stu-id="81b1b-124">Replays events in the order they were recorded.</span></span> <span data-ttu-id="81b1b-125">Esta opción habilita la depuración.</span><span class="sxs-lookup"><span data-stu-id="81b1b-125">This option enables debugging.</span></span>|  
    |<span data-ttu-id="81b1b-126">**Reproducir eventos mediante múltiples subprocesos**</span><span class="sxs-lookup"><span data-stu-id="81b1b-126">**Replay events using multiple threads**</span></span>|<span data-ttu-id="81b1b-127">Esta opción utiliza varios subprocesos para reproducir cada evento, independientemente de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="81b1b-127">This option uses multiple threads to replay each event regardless of the sequence.</span></span> <span data-ttu-id="81b1b-128">Esta opción optimiza el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="81b1b-128">This option optimizes performance.</span></span>|  
  
6.  <span data-ttu-id="81b1b-129">Seleccione **Mostrar resultados de la reproducción** para ver la reproducción mientras se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="81b1b-129">Select **Display replay results** to view the replay as it occurs.</span></span>  
  
7.  <span data-ttu-id="81b1b-130">Opcionalmente, haga clic en la pestaña **Opciones avanzadas de reproducción**para especificar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="81b1b-130">Optionally, click the **Advanced Replay Options**tab to specify the following options:</span></span>  
  
    -   <span data-ttu-id="81b1b-131">Para reproducir todos los identificadores de proceso de servidor (SPID), seleccione **Reproducir los SPID del sistema**.</span><span class="sxs-lookup"><span data-stu-id="81b1b-131">To replay all server process IDs (SPIDs), select **Replay system SPIDs**.</span></span>  
  
    -   <span data-ttu-id="81b1b-132">Para limitar la reproducción a los procesos que pertenecen a un determinado SPID, seleccione **Reproducir solo un SPID**.</span><span class="sxs-lookup"><span data-stu-id="81b1b-132">To limit the replay to processes belonging to a specific SPID, select **Replay one SPID only**.</span></span> <span data-ttu-id="81b1b-133">En el cuadro de diálogo **SPID para reproducir**escriba el SPID.</span><span class="sxs-lookup"><span data-stu-id="81b1b-133">In the **SPID to replay**box, type the SPID.</span></span>  
  
    -   <span data-ttu-id="81b1b-134">Para reproducir eventos producidos durante un determinado periodo, seleccione **Limitar reproducción por fecha y hora**.</span><span class="sxs-lookup"><span data-stu-id="81b1b-134">To replay events that occurred during a specific time period, select **Limit replay by date and time**.</span></span> <span data-ttu-id="81b1b-135">Seleccione una fecha y una hora en **Hora de inicio**y **Hora de finalización**para especificar el periodo que se incluirá en la reproducción.</span><span class="sxs-lookup"><span data-stu-id="81b1b-135">Select a date and time for the **Start time**and **End time**to specify the time period to include in the replay.</span></span>  
  
    -   <span data-ttu-id="81b1b-136">Para controlar el modo en que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administra los procesos durante la reproducción, configure **Opciones del monitor de estado**.</span><span class="sxs-lookup"><span data-stu-id="81b1b-136">To control how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] manages processes during replay, configure **Health Monitor Options**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b1b-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="81b1b-137">See Also</span></span>  
 <span data-ttu-id="81b1b-138">[Permisos necesarios para ejecutar SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="81b1b-138">[Permissions Required to Run SQL Server Profiler](sql-server-profiler.md) </span></span>  
 <span data-ttu-id="81b1b-139">[Reproducir seguimientos](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="81b1b-139">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="81b1b-140">[Abrir una tabla de seguimiento &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="81b1b-140">[Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="81b1b-141">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="81b1b-141">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
