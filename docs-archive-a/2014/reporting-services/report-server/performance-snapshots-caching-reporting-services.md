---
title: Rendimiento, instantáneas, almacenamiento en caché (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- performance [Reporting Services]
- Reporting Services, performance
ms.assetid: 85afd00f-e8d7-4ef7-9174-2ff84d82f960
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f171586e136b36bd694fa40b15272f62e1cb1378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746163"
---
# <a name="performance-snapshots-caching-reporting-services"></a><span data-ttu-id="9f2d9-102">Rendimiento, instantáneas, almacenamiento en caché (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="9f2d9-102">Performance, Snapshots, Caching (Reporting Services)</span></span>
  <span data-ttu-id="9f2d9-103">El rendimiento del servidor de informes se ve afectado por una combinación de factores entre los que se incluyen el hardware, el número de usuarios simultáneos que tienen acceso a los informes, la cantidad de datos de un informe y el formato de salida.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-103">Report server performance is affected by a combination of factors that include hardware, number of concurrent users accessing reports, the amount of data in a report, and output format.</span></span> <span data-ttu-id="9f2d9-104">Para entender los factores de rendimiento específicos de su instalación y qué remedios generarán los resultados que desea, necesitará obtener datos de línea base y ejecutar pruebas.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-104">To understand the performance factors that are specific to your installation and which remedies will produce the results you want, you will need to get baseline data and run tests.</span></span> <span data-ttu-id="9f2d9-105">Para obtener más información sobre herramientas e instrucciones, vea las publicaciones siguientes en MSDN: [Optimización del rendimiento de Reporting Services](https://blogs.msdn.com/b/sqlcat/archive/2013/10/30/reporting-services-performance-and-optimization.aspx) y [Usar Visual Studio 2005 para realizar pruebas de carga en un servidor de informes de SQL Server 2005 Reporting Services](https://go.microsoft.com/fwlink/?LinkID=77519).</span><span class="sxs-lookup"><span data-stu-id="9f2d9-105">For more information about tools and guidelines, see the following publications on MSDN: [Reporting Services Performance Optimization](https://blogs.msdn.com/b/sqlcat/archive/2013/10/30/reporting-services-performance-and-optimization.aspx) and [Using Visual Studio 2005 to Perform Load Testing on a SQL Server 2005 Reporting Services Report Server](https://go.microsoft.com/fwlink/?LinkID=77519).</span></span>  
  
 <span data-ttu-id="9f2d9-106">Entre los principios generales que hay que tener en cuenta se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9f2d9-106">General principles to consider include the following:</span></span>  
  
-   <span data-ttu-id="9f2d9-107">La representación y el procesamiento de informes consumen mucha memoria.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-107">Report processing and rendering are memory intensive operations.</span></span> <span data-ttu-id="9f2d9-108">Cuando sea posible, elija un equipo que tenga mucha memoria.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-108">When possible, choose a computer that has a lot of memory.</span></span>  
  
-   <span data-ttu-id="9f2d9-109">Hospedar el servidor de informes y la base de datos del servidor de informes en equipos independientes suele generar mejor rendimiento que hospedarlos en un único equipo de tecnología avanzada.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-109">Hosting the report server and the report server database on separate computers tends to provide better performance than hosting both on a single high-end computer.</span></span>  
  
-   <span data-ttu-id="9f2d9-110">Si todos los informes se procesan despacio, piense en una implementación escalada donde varias instancias del servidor de informes admitan una única base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-110">If all reports are processing slowly, consider a scale-out deployment where multiple report server instances support a single report server database.</span></span> <span data-ttu-id="9f2d9-111">Para obtener mejores resultados, use el software de equilibrio de carga para distribuir solicitudes de forma uniforme en la implementación.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-111">For best results, use load balancing software to distribute requests evenly across the deployment.</span></span>  
  
-   <span data-ttu-id="9f2d9-112">Si un solo informe se procesa con lentitud, ajuste las consultas del conjunto de datos del informe si este debe ejecutarse a petición.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-112">If a single report is processing slowly, tune report dataset queries if the report must run on demand.</span></span> <span data-ttu-id="9f2d9-113">También podría considerar usar conjuntos de datos compartidos que pueda almacenar en memoria caché, almacenar en memoria caché el informe o ejecutarlo como una instantánea.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-113">You might also consider using shared datasets that you can cache, caching the report, or running the report as a snapshot.</span></span>  
  
-   <span data-ttu-id="9f2d9-114">Si todos los informes se procesan en un formato concreto (por ejemplo, al representarse en PDF), piense en la entrega a recursos compartidos de archivos, en agregar más memoria o en elegir un formato diferente.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-114">If all reports process slowly in a specific format (for example, while rendering to PDF), consider file share delivery, adding more memory, or choosing a different format.</span></span>  
  
-   <span data-ttu-id="9f2d9-115">Para averiguar cuánto tiempo se tarda en procesar un informe y otras métricas de uso, revise el registro de ejecución del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-115">To find out how long it takes to process a report and other usage metrics, review the report server execution log.</span></span> <span data-ttu-id="9f2d9-116">Para obtener más información, vea [registro de ejecución del servidor de informes y la vista ExecutionLog3](report-server-executionlog-and-the-executionlog3-view.md).</span><span class="sxs-lookup"><span data-stu-id="9f2d9-116">For more information, see [Report Server Execution Log and the ExecutionLog3 View](report-server-executionlog-and-the-executionlog3-view.md).</span></span>  
  
-   <span data-ttu-id="9f2d9-117">Para más información sobre cómo reducir los problemas de rendimiento con la configuración de la administración de la memoria, vea [Configurar la memoria disponible para aplicaciones del servidor de informes](../report-server/configure-available-memory-for-report-server-applications.md).</span><span class="sxs-lookup"><span data-stu-id="9f2d9-117">For more information about how to mitigate performance issues by tuning memory management configuration settings, see [Configure Available Memory for Report Server Applications](../report-server/configure-available-memory-for-report-server-applications.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f2d9-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9f2d9-118">In This Section</span></span>  
 [<span data-ttu-id="9f2d9-119">Supervisión del rendimiento del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="9f2d9-119">Monitoring Report Server Performance</span></span>](monitoring-report-server-performance.md)  
 <span data-ttu-id="9f2d9-120">Describe los objetos de rendimiento que puede usar para realizar un seguimiento de la carga de procesamiento en su servidor.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-120">Describes the performance objects you can use to track the processing load on your server.</span></span>  
  
 [<span data-ttu-id="9f2d9-121">Establecimiento de las propiedades del procesamiento de informes</span><span class="sxs-lookup"><span data-stu-id="9f2d9-121">Set Report Processing Properties</span></span>](set-report-processing-properties.md)  
 <span data-ttu-id="9f2d9-122">Describe los modos de configuración de un informe para ejecutarlo a petición, desde la memoria caché, o en función de una programación como una instantánea de informe.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-122">Describes ways of configuring a report to run on demand, from cache, or on a schedule as a report snapshot.</span></span>  
  
 [<span data-ttu-id="9f2d9-123">Configuración de la memoria disponible para las aplicaciones del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="9f2d9-123">Configure Available Memory for Report Server Applications</span></span>](../report-server/configure-available-memory-for-report-server-applications.md)  
 <span data-ttu-id="9f2d9-124">Describe cómo puede invalidar el comportamiento predeterminado de administración de memoria.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-124">Describes how you can override default memory management behavior.</span></span>  
  
 [<span data-ttu-id="9f2d9-125">Informes almacenados en caché &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9f2d9-125">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
 <span data-ttu-id="9f2d9-126">Describe el comportamiento del almacenamiento en caché de los informes de un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-126">Describes report caching behavior on a report server.</span></span>  
  
 [<span data-ttu-id="9f2d9-127">Almacenar en caché conjuntos de datos compartidos &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9f2d9-127">Cache Shared Datasets &#40;SSRS&#41;</span></span>](cache-shared-datasets-ssrs.md)  
 <span data-ttu-id="9f2d9-128">Describe el comportamiento del almacenamiento en caché de conjuntos de datos compartidos en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-128">Describes shared dataset caching behavior on a report server.</span></span>  
  
 [<span data-ttu-id="9f2d9-129">Procesamiento de informes grandes</span><span class="sxs-lookup"><span data-stu-id="9f2d9-129">Process Large Reports</span></span>](process-large-reports.md)  
 <span data-ttu-id="9f2d9-130">Proporciona recomendaciones sobre cómo configurar y distribuir un informe de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-130">Provides recommendations on how to configure and distribute a large report.</span></span>  
  
 [<span data-ttu-id="9f2d9-131">Establecer valores de tiempo de espera para el procesamiento de informes y conjuntos de datos compartidos &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9f2d9-131">Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;</span></span>](setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md)  
 <span data-ttu-id="9f2d9-132">Explica cómo establecer los tiempos de espera para el procesamiento de informes y de consultas.</span><span class="sxs-lookup"><span data-stu-id="9f2d9-132">Explains how to set time outs on query and report processing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f2d9-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9f2d9-133">See Also</span></span>  
 <span data-ttu-id="9f2d9-134">[Administrar un proceso en ejecución](../subscriptions/manage-a-running-process.md) </span><span class="sxs-lookup"><span data-stu-id="9f2d9-134">[Manage a Running Process](../subscriptions/manage-a-running-process.md) </span></span>  
 [<span data-ttu-id="9f2d9-135">Verificación de la ejecución de un informe</span><span class="sxs-lookup"><span data-stu-id="9f2d9-135">Verifying a Report Run</span></span>](verifying-a-report-run.md)  
  
  
