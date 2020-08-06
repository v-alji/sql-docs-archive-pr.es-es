---
title: Reproducir un archivo de seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 9e361275-c8fd-4499-8389-242cf8e27415
author: stevestein
ms.author: sstein
ms.openlocfilehash: d3a9f007b9b6d2b46be43abdb10db286a75c33fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748411"
---
# <a name="replay-a-trace-file-sql-server-profiler"></a><span data-ttu-id="cefe7-102">Reproducir un archivo de seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="cefe7-102">Replay a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="cefe7-103">La reproducción es la capacidad de abrir un seguimiento guardado y reproducirlo más tarde.</span><span class="sxs-lookup"><span data-stu-id="cefe7-103">Replay is the ability to open a saved trace and replay it again.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="cefe7-104">incluye un motor de reproducción de varios subprocesos que puede simular conexiones de usuario y la Autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cefe7-104">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="cefe7-105">La reproducción es útil para solucionar problemas de aplicaciones o procesos.</span><span class="sxs-lookup"><span data-stu-id="cefe7-105">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="cefe7-106">Cuando identifique el problema e implemente las acciones para corregirlo, ejecute el seguimiento que encontró el posible problema en la aplicación o proceso corregido.</span><span class="sxs-lookup"><span data-stu-id="cefe7-106">When you identify the problem and implement corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="cefe7-107">A continuación, reproduzca el seguimiento original y compare los resultados.</span><span class="sxs-lookup"><span data-stu-id="cefe7-107">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="cefe7-108">Además de otras clases de eventos que desee supervisar, debe capturar clases de eventos específicas para habilitar la reproducción:</span><span class="sxs-lookup"><span data-stu-id="cefe7-108">In addition to any other event classes you want to monitor, specific event classes must be captured to enable replay.</span></span> <span data-ttu-id="cefe7-109">Estos eventos se capturan de forma predeterminada si se usa la plantilla de seguimiento **TSQL_Replay** .</span><span class="sxs-lookup"><span data-stu-id="cefe7-109">These events are captured by default if you use the **TSQL_Replay** trace template.</span></span> <span data-ttu-id="cefe7-110">Para más información, consulte [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cefe7-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
### <a name="to-replay-a-trace-file"></a><span data-ttu-id="cefe7-111">Para reproducir un archivo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="cefe7-111">To replay a trace file</span></span>  
  
1.  <span data-ttu-id="cefe7-112">En el menú **Archivo** , seleccione **Abrir**y, a continuación, haga clic en **Archivo de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="cefe7-112">On the **File** menu, point to **Open**, and then click **Trace File**.</span></span> <span data-ttu-id="cefe7-113">Seleccione un archivo de seguimiento que contenga las clases de eventos necesarias para la reproducción.</span><span class="sxs-lookup"><span data-stu-id="cefe7-113">Select a trace file that contains the event classes necessary for replay.</span></span>  
  
2.  <span data-ttu-id="cefe7-114">En el menú **Reproducir** , haga clic en **Iniciar**y conéctese a la instancia del servidor en la que desee reproducir el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="cefe7-114">On the **Replay** menu, click **Start**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="cefe7-115">En el cuadro de diálogo **Configuración de reproducción** , en la pestaña **Opciones básicas de reproducción** , especifique **Servidor de reproducción**.</span><span class="sxs-lookup"><span data-stu-id="cefe7-115">In the **Replay Configuration** dialog box, on the **Basic Replay Options** tab, specify the **Replay server**.</span></span> <span data-ttu-id="cefe7-116">Haga clic en **Cambiar** para cambiar el servidor visualizado en el cuadro **Servidor de reproducción** .</span><span class="sxs-lookup"><span data-stu-id="cefe7-116">Click **Change** to change the server displayed in the **Replay server** box.</span></span>  
  
4.  <span data-ttu-id="cefe7-117">Opcionalmente, seleccione uno de los siguientes destinos para guardar la reproducción:</span><span class="sxs-lookup"><span data-stu-id="cefe7-117">Optionally, select one of the following destinations in which to save the replay:</span></span>  
  
    -   <span data-ttu-id="cefe7-118">**Guardar en el archivo**, que especifica un archivo en el que se guardará la reproducción.</span><span class="sxs-lookup"><span data-stu-id="cefe7-118">**Save to file**, which specifies a file in which to save the replay.</span></span>  
  
    -   <span data-ttu-id="cefe7-119">**Guardar en la tabla**, que especifica una tabla de base de datos en la que se guardará la reproducción.</span><span class="sxs-lookup"><span data-stu-id="cefe7-119">**Save to table**, which specifies a database table in which to save the replay.</span></span>  
  
5.  <span data-ttu-id="cefe7-120">Elija **Reproducir eventos en el oden de seguimiento**o **Reproducir eventos mediante múltiples subprocesos**.</span><span class="sxs-lookup"><span data-stu-id="cefe7-120">Choose either **Replay the events in the order they were traced**or **Replay events using multiple threads**.</span></span> <span data-ttu-id="cefe7-121">En la tabla siguiente se explica la diferencia entre estas opciones.</span><span class="sxs-lookup"><span data-stu-id="cefe7-121">The following table explains the difference between these settings.</span></span>  
  
    |<span data-ttu-id="cefe7-122">Opción</span><span class="sxs-lookup"><span data-stu-id="cefe7-122">Option</span></span>|<span data-ttu-id="cefe7-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="cefe7-123">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="cefe7-124">**Reproducir eventos en el orden del seguimiento**</span><span class="sxs-lookup"><span data-stu-id="cefe7-124">**Replay events in the order they were traced**</span></span>|<span data-ttu-id="cefe7-125">Reproduce los eventos en el orden en que se registraron.</span><span class="sxs-lookup"><span data-stu-id="cefe7-125">Replays events in the order they were recorded.</span></span> <span data-ttu-id="cefe7-126">Esta opción habilita la depuración.</span><span class="sxs-lookup"><span data-stu-id="cefe7-126">This option enables debugging.</span></span>|  
    |<span data-ttu-id="cefe7-127">**Reproducir eventos mediante múltiples subprocesos**</span><span class="sxs-lookup"><span data-stu-id="cefe7-127">**Replay events using multiple threads**</span></span>|<span data-ttu-id="cefe7-128">Esta opción utiliza varios subprocesos para reproducir cada evento, independientemente de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="cefe7-128">This option uses multiple threads to replay each event regardless of the sequence.</span></span> <span data-ttu-id="cefe7-129">Esta opción optimiza el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="cefe7-129">This option optimizes performance.</span></span>|  
  
6.  <span data-ttu-id="cefe7-130">Seleccione **Mostrar resultados de la reproducción** para ver la reproducción mientras se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="cefe7-130">Select **Display replay results** to view the replay as it occurs.</span></span>  
  
7.  <span data-ttu-id="cefe7-131">Si lo desea, haga clic en la pestaña **Opciones avanzadas de reproducción**para configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="cefe7-131">Optionally click the **Advanced Replay Options**tab to configure the following options:</span></span>  
  
    -   <span data-ttu-id="cefe7-132">Para reproducir todos los identificadores de proceso de servidor (SPID), seleccione **Reproducir los SPID del sistema**.</span><span class="sxs-lookup"><span data-stu-id="cefe7-132">To replay all server process IDs (SPIDs), select **Replay system SPIDs**.</span></span>  
  
    -   <span data-ttu-id="cefe7-133">Para limitar la reproducción a los procesos que pertenecen a un determinado SPID, seleccione **Reproducir solo un SPID**.</span><span class="sxs-lookup"><span data-stu-id="cefe7-133">To limit the replay to processes belonging to a specific SPID, select **Replay one SPID only**.</span></span> <span data-ttu-id="cefe7-134">En el cuadro **SPID para reproducir** , escriba el SPID.</span><span class="sxs-lookup"><span data-stu-id="cefe7-134">In the **SPID to replay** box, type the SPID.</span></span>  
  
    -   <span data-ttu-id="cefe7-135">Para reproducir eventos producidos durante un determinado periodo, seleccione **Limitar reproducción por fecha y hora**.</span><span class="sxs-lookup"><span data-stu-id="cefe7-135">To replay events that occurred during a specific time period, select **Limit the replay by date and time**.</span></span> <span data-ttu-id="cefe7-136">Seleccione una fecha y una hora en **Hora de inicio**y **Hora de finalización**para especificar el periodo que se incluirá en la reproducción.</span><span class="sxs-lookup"><span data-stu-id="cefe7-136">Select a date and time for the **Start time**and **End time**to specify the time period to include in the replay.</span></span>  
  
    -   <span data-ttu-id="cefe7-137">Para controlar el modo en que SQL Server administra los procesos durante la reproducción, configure **Opciones del monitor de estado**.</span><span class="sxs-lookup"><span data-stu-id="cefe7-137">To control how SQL Server manages processes during replay, configure **Health Monitor Options**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cefe7-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cefe7-138">See Also</span></span>  
 <span data-ttu-id="cefe7-139">[Permisos necesarios para ejecutar SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="cefe7-139">[Permissions Required to Run SQL Server Profiler](sql-server-profiler.md) </span></span>  
 <span data-ttu-id="cefe7-140">[Reproducir seguimientos](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="cefe7-140">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="cefe7-141">[Abrir un archivo de seguimiento &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="cefe7-141">[Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="cefe7-142">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="cefe7-142">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
