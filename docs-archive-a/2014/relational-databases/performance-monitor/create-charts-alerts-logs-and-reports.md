---
title: Creación de gráficos, alertas, registros e informes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- System Monitor [SQL Server], charts and reports
- charts [SQL Server]
- reports [SQL Server]
- reports [SQL Server], creating
- Windows System Monitor [SQL Server], charts and reports
- logs [SQL Server], System Monitor
- System Monitor [SQL Server], logs
- Windows System Monitor [SQL Server], logs
ms.assetid: c9162b37-e5dc-43d1-a3aa-1e9ebc69fecc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3a0c95c3f483a8af3e3e68d9c5c7d3caf44350d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749247"
---
# <a name="create-charts-alerts-logs-and-reports"></a><span data-ttu-id="5fb79-102">Crear gráficos, alertas, registros e informes</span><span class="sxs-lookup"><span data-stu-id="5fb79-102">Create Charts, Alerts, Logs, and Reports</span></span>
  <span data-ttu-id="5fb79-103">El Monitor de sistema le permite crear gráficos, alertas, registros e informes para supervisar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fb79-103">System Monitor lets you create charts, alerts, logs, and reports to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="charts"></a><span data-ttu-id="5fb79-104">Gráficos</span><span class="sxs-lookup"><span data-stu-id="5fb79-104">Charts</span></span>  
 <span data-ttu-id="5fb79-105">Los gráficos pueden supervisar el rendimiento actual de los objetos y contadores seleccionados; por ejemplo, el uso de la CPU o la E/S de disco.</span><span class="sxs-lookup"><span data-stu-id="5fb79-105">Charts can monitor the current performance of selected objects and counters; for example, the CPU usage or disk I/O.</span></span> <span data-ttu-id="5fb79-106">Puede agregar a un gráfico varias combinaciones de objetos y contadores del Monitor de sistema</span><span class="sxs-lookup"><span data-stu-id="5fb79-106">You can add to a chart various combinations of System Monitor objects and counters.</span></span> <span data-ttu-id="5fb79-107">También puede agregar objetos y contadores de [!INCLUDE[msCoName](../../includes/msconame-md.md)] a un gráfico.</span><span class="sxs-lookup"><span data-stu-id="5fb79-107">You also can add [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows objects and counters to a chart.</span></span>  
  
 <span data-ttu-id="5fb79-108">Cada gráfico representa un subconjunto de información que desea supervisar.</span><span class="sxs-lookup"><span data-stu-id="5fb79-108">Each chart represents a subset of information you want to monitor.</span></span> <span data-ttu-id="5fb79-109">Por ejemplo, mediante un gráfico puede realizar el seguimiento de las estadísticas relativas al uso de la memoria y, con otro gráfico, el seguimiento de las estadísticas relativas a la E/S de disco.</span><span class="sxs-lookup"><span data-stu-id="5fb79-109">For example, one chart can track memory usage statistics and a second chart can track disk I/O statistics.</span></span>  
  
 <span data-ttu-id="5fb79-110">El uso de gráficos puede resultar útil para realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="5fb79-110">Using a chart can be useful for the following tasks:</span></span>  
  
-   <span data-ttu-id="5fb79-111">Investigar las causas de la lentitud o la ineficacia de equipos o aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5fb79-111">Investigating why a computer or application is slow or inefficient.</span></span>  
  
-   <span data-ttu-id="5fb79-112">Supervisar sistemas de manera continua para buscar problemas de rendimiento intermitentes.</span><span class="sxs-lookup"><span data-stu-id="5fb79-112">Continually monitoring systems to find intermittent performance problems.</span></span>  
  
-   <span data-ttu-id="5fb79-113">Descubrir las causas de la necesidad de aumentar la capacidad.</span><span class="sxs-lookup"><span data-stu-id="5fb79-113">Discovering why you need to increase capacity.</span></span>  
  
-   <span data-ttu-id="5fb79-114">Mostrar una tendencia como un gráfico de líneas.</span><span class="sxs-lookup"><span data-stu-id="5fb79-114">Displaying a trend as a line chart.</span></span>  
  
-   <span data-ttu-id="5fb79-115">Mostrar comparaciones en histogramas.</span><span class="sxs-lookup"><span data-stu-id="5fb79-115">Displaying a comparison as a histogram chart.</span></span>  
  
 <span data-ttu-id="5fb79-116">Los gráficos son útiles para la supervisión a corto plazo en tiempo real de equipos locales o remotos, por ejemplo, cuando se desea supervisar un evento a medida que se produce.</span><span class="sxs-lookup"><span data-stu-id="5fb79-116">Charts are useful for short-term, real-time monitoring of a local or remote computer (for example, when you want to monitor an event as it occurs).</span></span>  
  
## <a name="alerts"></a><span data-ttu-id="5fb79-117">Alertas</span><span class="sxs-lookup"><span data-stu-id="5fb79-117">Alerts</span></span>  
 <span data-ttu-id="5fb79-118">Mediante las alertas, el Monitor de sistema realiza un seguimiento de eventos específicos y le notifica dichos eventos cuando lo solicite.</span><span class="sxs-lookup"><span data-stu-id="5fb79-118">Using alerts, System Monitor tracks specific events and notifies you of these events as requested.</span></span> <span data-ttu-id="5fb79-119">El registro de alertas permite supervisar el rendimiento actual de contadores e instancias seleccionados de objetos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fb79-119">An alert log can monitor the current performance of selected counters and instances for objects in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5fb79-120">Cuando un contador supera un valor determinado, se guardan en el registro la fecha y hora del evento.</span><span class="sxs-lookup"><span data-stu-id="5fb79-120">When a counter exceeds a given value, the log records the date and time of the event.</span></span> <span data-ttu-id="5fb79-121">Un evento también puede generar una alerta de red.</span><span class="sxs-lookup"><span data-stu-id="5fb79-121">An event can also generate a network alert.</span></span> <span data-ttu-id="5fb79-122">Puede establecer la ejecución de un programa específico la primera vez o cada vez que se produzca un evento.</span><span class="sxs-lookup"><span data-stu-id="5fb79-122">You can have a specified program run the first time or every time an event occurs.</span></span> <span data-ttu-id="5fb79-123">Por ejemplo, una alerta puede enviar un mensaje de red a todos los administradores del sistema acerca de que la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se está quedando sin espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="5fb79-123">For example, an alert can send a network message to all system administrators that the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is getting low on disk space.</span></span>  
  
## <a name="logs"></a><span data-ttu-id="5fb79-124">Registros</span><span class="sxs-lookup"><span data-stu-id="5fb79-124">Logs</span></span>  
 <span data-ttu-id="5fb79-125">Los registros permiten grabar información acerca de la actividad actual de objetos y equipos seleccionados para su posterior presentación y análisis.</span><span class="sxs-lookup"><span data-stu-id="5fb79-125">Logs allow you to record information on the current activity of selected objects and computers for later viewing and analysis.</span></span> <span data-ttu-id="5fb79-126">Puede recopilar datos de múltiples sistemas en un único archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="5fb79-126">You can collect data from multiple systems into a single log file.</span></span> <span data-ttu-id="5fb79-127">Por ejemplo, puede crear diferentes registros para acumular información acerca del rendimiento de objetos seleccionados en diversos equipos para su posterior análisis.</span><span class="sxs-lookup"><span data-stu-id="5fb79-127">For example, you can create different logs to accumulate information about the performance of selected objects on various computers for future analysis.</span></span> <span data-ttu-id="5fb79-128">Asimismo, puede guardar estas selecciones en un archivo y volverlas a utilizar cuando desee crear otro registro con información similar para realizar una comparación.</span><span class="sxs-lookup"><span data-stu-id="5fb79-128">You can save these selections under a file name and reuse them when you want to create another log of similar information for comparison.</span></span>  
  
 <span data-ttu-id="5fb79-129">Los archivos de registro proporcionan una gran cantidad de información para la solución de problemas y el planeamiento.</span><span class="sxs-lookup"><span data-stu-id="5fb79-129">Log files provide a wealth of information for troubleshooting or planning.</span></span> <span data-ttu-id="5fb79-130">Mientras que los gráficos, alertas e informes acerca de la actividad actual proporcionan una evaluación instantánea, los archivos de registro permiten realizar un seguimiento de los contadores durante un largo período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="5fb79-130">Whereas charts, alerts, and reports on current activity provide instant feedback, log files enable you to track counters over a long period of time.</span></span> <span data-ttu-id="5fb79-131">Por tanto, puede analizar la información más exhaustivamente y documentar el rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="5fb79-131">Thus, you can examine information more thoroughly and document system performance.</span></span>  
  
## <a name="reports"></a><span data-ttu-id="5fb79-132">Informes</span><span class="sxs-lookup"><span data-stu-id="5fb79-132">Reports</span></span>  
 <span data-ttu-id="5fb79-133">Los informes permiten mostrar el cambio continuo en los valores de contadores e instancias de los objetos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="5fb79-133">Reports allow you to display constantly changing counter and instance values for selected objects.</span></span> <span data-ttu-id="5fb79-134">Los valores se muestran en columnas para cada instancia.</span><span class="sxs-lookup"><span data-stu-id="5fb79-134">Values appear in columns for each instance.</span></span> <span data-ttu-id="5fb79-135">Puede ajustar los intervalos de informes, imprimir instantáneas y exportar datos.</span><span class="sxs-lookup"><span data-stu-id="5fb79-135">You can adjust report intervals, print snapshots, and export data.</span></span> <span data-ttu-id="5fb79-136">Utilice informes cuando necesite mostrar los números sin procesar.</span><span class="sxs-lookup"><span data-stu-id="5fb79-136">Use reports when you need to display the raw numbers.</span></span>  
  
 <span data-ttu-id="5fb79-137">Para obtener más información acerca de la creación gráficos, alertas, registros e informes, o acerca de objetos y contadores de Windows, consulte la documentación de Windows.</span><span class="sxs-lookup"><span data-stu-id="5fb79-137">For more information about creating charts, alerts, logs, and reports, or about Windows objects and counters, see the Windows documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb79-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5fb79-138">See Also</span></span>  
 [<span data-ttu-id="5fb79-139">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb79-139">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
