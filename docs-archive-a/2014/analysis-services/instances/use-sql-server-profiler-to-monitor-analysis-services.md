---
title: Usar SQL Server Profiler para supervisar Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, Analysis Services
- monitoring Analysis Services [SQL Server]
- performance [Analysis Services], SQL Server Profiler
- Profiler [SQL Server Profiler], Analysis Services
ms.assetid: 8b77dafc-4584-4e93-8ad7-299304391bfd
author: minewiskan
ms.author: owend
ms.openlocfilehash: e144c1d858670f8a46b164ffc9885e6e082c4b0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669956"
---
# <a name="use-sql-server-profiler-to-monitor-analysis-services"></a><span data-ttu-id="967f0-102">Usar SQL Server Profiler para supervisar Analysis Services</span><span class="sxs-lookup"><span data-stu-id="967f0-102">Use SQL Server Profiler to Monitor Analysis Services</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="967f0-103">realiza un seguimiento de los eventos de procesos del motor, como el inicio de un lote o una transacción, y captura datos sobre estos eventos, lo que permite supervisar la actividad del servidor y de la base de datos (por ejemplo, consultas del usuario o actividad de inicio de sesión).</span><span class="sxs-lookup"><span data-stu-id="967f0-103">tracks engine process events, such as the start of a batch or a transaction, and it captures data about those events, thus enabling you to monitor server and database activity (for example, user queries or login activity).</span></span> <span data-ttu-id="967f0-104">Puede capturar datos del [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] en un archivo o una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para su análisis posterior y también reproducir los eventos capturados en la misma instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o en otra, para ver qué sucedió exactamente.</span><span class="sxs-lookup"><span data-stu-id="967f0-104">You can capture [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] data to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or a file for later analysis, and you can also replay the events captured on the same or another [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance to see exactly what happened.</span></span> <span data-ttu-id="967f0-105">Puede reproducir eventos en tiempo real o paso a paso.</span><span class="sxs-lookup"><span data-stu-id="967f0-105">You can replay events in real time or on a step-by-step basis.</span></span> <span data-ttu-id="967f0-106">También resulta útil ejecutar los eventos de seguimiento junto con los contadores de Rendimiento en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="967f0-106">It is also very useful to run the trace events along with the Performance counters on the same machine.</span></span> <span data-ttu-id="967f0-107">El analizador puede correlacionar los dos basándose en el tiempo y mostrarlos juntos en una misma línea temporal.</span><span class="sxs-lookup"><span data-stu-id="967f0-107">The profiler can correlate these two based on time and display them together along a single timeline.</span></span> <span data-ttu-id="967f0-108">Los eventos de seguimiento proporcionan más detalles, mientras que los contadores de Rendimiento ofrecen una vista agregada.</span><span class="sxs-lookup"><span data-stu-id="967f0-108">Trace events will give you more details while Performance counters give you an aggregate view.</span></span> <span data-ttu-id="967f0-109">Para obtener información sobre cómo crear y ejecutar seguimientos, vea [Crear seguimientos del generador de perfiles para su reproducción &#40;Analysis Services&#41;](create-profiler-traces-for-replay-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="967f0-109">For information about how to create and run traces, see [Create Profiler Traces for Replay &#40;Analysis Services&#41;](create-profiler-traces-for-replay-analysis-services.md).</span></span>  
  
 <span data-ttu-id="967f0-110">En la tabla siguiente se describen los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="967f0-110">The following table describes the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="967f0-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="967f0-111">In This Section</span></span>  
  
|<span data-ttu-id="967f0-112">Tema</span><span class="sxs-lookup"><span data-stu-id="967f0-112">Topic</span></span>|<span data-ttu-id="967f0-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="967f0-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="967f0-114">Introducción a Supervisar Analysis Services con SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="967f0-114">Introduction to Monitoring Analysis Services with SQL Server Profiler</span></span>](introduction-to-monitoring-analysis-services-with-sql-server-profiler.md)|<span data-ttu-id="967f0-115">Describe cómo utilizar el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para supervisar una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="967f0-115">Describes how to use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to monitor an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>|  
|[<span data-ttu-id="967f0-116">Crear seguimientos del generador de perfiles para su reproducción &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="967f0-116">Create Profiler Traces for Replay &#40;Analysis Services&#41;</span></span>](create-profiler-traces-for-replay-analysis-services.md)|<span data-ttu-id="967f0-117">Describe los requisitos para crear un seguimiento para la reproducción mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="967f0-117">Describes the requirements for creating a trace for replay by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="967f0-118">Eventos de seguimiento de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="967f0-118">Analysis Services Trace Events</span></span>](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events)|<span data-ttu-id="967f0-119">Describe las clases de evento de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="967f0-119">Describes [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] event classes.</span></span> <span data-ttu-id="967f0-120">Estas clases de evento se asignan a las acciones generadas por [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y se utilizan para las reproducciones de seguimientos.</span><span class="sxs-lookup"><span data-stu-id="967f0-120">These event classes map to actions generated by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and are used for trace replays.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="967f0-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="967f0-121">See Also</span></span>  
 [<span data-ttu-id="967f0-122">Monitor an Analysis Services Instance</span><span class="sxs-lookup"><span data-stu-id="967f0-122">Monitor an Analysis Services Instance</span></span>](monitor-an-analysis-services-instance.md)  
  
  
