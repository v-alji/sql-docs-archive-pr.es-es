---
title: Usar la sesión system_health | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], system health session
- extended events [SQL Server], system_health session
- system_health session [SQL Server extended events]
- system health session [SQL Server extended events]
ms.assetid: 1e1fad43-d747-4775-ac0d-c50648e56d78
author: yualan
ms.author: alayu
ms.openlocfilehash: 86c3221fb4c0ea0690b369888ac8f2f9f82d6ef9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662918"
---
# <a name="use-the-system_health-session"></a><span data-ttu-id="275b1-102">Usar la sesión system_health</span><span class="sxs-lookup"><span data-stu-id="275b1-102">Use the system_health Session</span></span>
  <span data-ttu-id="275b1-103">La sesión system_health es una sesión de eventos extendidos que se incluye de forma predeterminada con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="275b1-103">The system_health session is an Extended Events session that is included by default with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="275b1-104">Esta sesión se inicia automáticamente cuando [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] se inicia, y se ejecuta sin ningún efecto de rendimiento notable.</span><span class="sxs-lookup"><span data-stu-id="275b1-104">This session starts automatically when the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] starts, and runs without any noticeable performance effects.</span></span> <span data-ttu-id="275b1-105">La sesión recopila datos del sistema que se pueden utilizar para ayudar a solucionar problemas de rendimiento en el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="275b1-105">The session collects system data that you can use to help troubleshoot performance issues in the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="275b1-106">Por consiguiente, se recomienda no detener ni eliminar la sesión.</span><span class="sxs-lookup"><span data-stu-id="275b1-106">Therefore, we recommend that you do not stop or delete the session.</span></span>  
  
 <span data-ttu-id="275b1-107">La sesión recopila información como la que se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="275b1-107">The session collects information that includes the following:</span></span>  
  
-   <span data-ttu-id="275b1-108">sql_text y session_id para las sesiones que encuentran un error cuya gravedad es >= 20.</span><span class="sxs-lookup"><span data-stu-id="275b1-108">The sql_text and session_id for any sessions that encounter an error that has a severity >=20.</span></span>  
  
-   <span data-ttu-id="275b1-109">sql_text y session_id para las sesiones que encuentran un error relacionado con la memoria.</span><span class="sxs-lookup"><span data-stu-id="275b1-109">The sql_text and session_id for any sessions that encounter a memory-related error.</span></span> <span data-ttu-id="275b1-110">Entre los errores se incluyen 17803, 701, 802, 8645, 8651, 8657 y 8902.</span><span class="sxs-lookup"><span data-stu-id="275b1-110">The errors include 17803, 701, 802, 8645, 8651, 8657 and 8902.</span></span>  
  
-   <span data-ttu-id="275b1-111">Un registro de los problemas de un programador que no rinde.</span><span class="sxs-lookup"><span data-stu-id="275b1-111">A record of any non-yielding scheduler problems.</span></span> <span data-ttu-id="275b1-112">(Estos aparecen en el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como error 17883).</span><span class="sxs-lookup"><span data-stu-id="275b1-112">(These appear in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log as error 17883.)</span></span>  
  
-   <span data-ttu-id="275b1-113">Los interbloqueos detectados.</span><span class="sxs-lookup"><span data-stu-id="275b1-113">Any deadlocks that are detected.</span></span>  
  
-   <span data-ttu-id="275b1-114">callstack, sql_text y session_id para las sesiones que han esperado en bloqueos temporales (u otros recursos interesantes) durante > 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="275b1-114">The callstack, sql_text, and session_id for any sessions that have waited on latches (or other interesting resources) for > 15 seconds.</span></span>  
  
-   <span data-ttu-id="275b1-115">callstack, sql_text y session_id para las sesiones que han esperado en bloqueos durante > 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="275b1-115">The callstack, sql_text, and session_id for any sessions that have waited on locks for > 30 seconds.</span></span>  
  
-   <span data-ttu-id="275b1-116">callstack, sql_text y session_id para las sesiones que han esperado mucho tiempo a causa de esperas preferentes.</span><span class="sxs-lookup"><span data-stu-id="275b1-116">The callstack, sql_text, and session_id for any sessions that have waited for a long time for preemptive waits.</span></span> <span data-ttu-id="275b1-117">La duración varía en función del tipo de espera.</span><span class="sxs-lookup"><span data-stu-id="275b1-117">The duration varies by wait type.</span></span> <span data-ttu-id="275b1-118">Una espera preferente es aquella en que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está esperando llamadas a API externas.</span><span class="sxs-lookup"><span data-stu-id="275b1-118">A preemptive wait is where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is waiting for external API calls.</span></span>  
  
-   <span data-ttu-id="275b1-119">La pila de llamadas y el session_id para los errores de las asignaciones virtuales y de CLR.</span><span class="sxs-lookup"><span data-stu-id="275b1-119">The callstack and session_id for CLR allocation and virtual allocation failures.</span></span>  
  
-   <span data-ttu-id="275b1-120">Los eventos ring_buffer para el agente de memoria, el supervisor del programador, el OOM del nodo de memoria, la seguridad y la conectividad.</span><span class="sxs-lookup"><span data-stu-id="275b1-120">The ring_buffer events for the memory broker, scheduler monitor, memory node OOM, security, and connectivity.</span></span>  
  
-   <span data-ttu-id="275b1-121">Los resultados de los componentes del sistema de sp_server_diagnostics.</span><span class="sxs-lookup"><span data-stu-id="275b1-121">System component results from sp_server_diagnostics.</span></span>  
  
-   <span data-ttu-id="275b1-122">Estado de la instancia recopilado por scheduler_monitor_system_health_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="275b1-122">Instance health collected by scheduler_monitor_system_health_ring_buffer_recorded.</span></span>  
  
-   <span data-ttu-id="275b1-123">Errores en la asignación de CLR.</span><span class="sxs-lookup"><span data-stu-id="275b1-123">CLR Allocation failures.</span></span>  
  
-   <span data-ttu-id="275b1-124">Errores de conectividad utilizando connectivity_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="275b1-124">Connectivity errors using connectivity_ring_buffer_recorded.</span></span>  
  
-   <span data-ttu-id="275b1-125">Errores de seguridad utilizando security_error_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="275b1-125">Security errors using security_error_ring_buffer_recorded.</span></span>  
  
## <a name="viewing-the-session-data"></a><span data-ttu-id="275b1-126">Ver los datos de la sesión</span><span class="sxs-lookup"><span data-stu-id="275b1-126">Viewing the Session Data</span></span>  
 <span data-ttu-id="275b1-127">La sesión utiliza el destino del búfer en anillo para almacenar los datos.</span><span class="sxs-lookup"><span data-stu-id="275b1-127">The session uses the ring buffer target to store the data.</span></span> <span data-ttu-id="275b1-128">Para ver los datos de la sesión, utilice la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="275b1-128">To view the session data, use the following query:</span></span>  
  
```  
SELECT CAST(xet.target_data as xml) FROM sys.dm_xe_session_targets xet  
JOIN sys.dm_xe_sessions xe  
ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'system_health'  
```  
  
 <span data-ttu-id="275b1-129">Para ver los datos de sesión del archivo de eventos, use la interfaz de usuario Eventos extendidos disponible en Management Studio.</span><span class="sxs-lookup"><span data-stu-id="275b1-129">To view the session data from the event file, use the Extended Events user interface available in Management Studio.</span></span> <span data-ttu-id="275b1-130">Consulte [View Event Session Data](../../database-engine/view-event-session-data.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="275b1-130">See [View Event Session Data](../../database-engine/view-event-session-data.md) for more information.</span></span>  
  
## <a name="restoring-the-system_health-session"></a><span data-ttu-id="275b1-131">Restaurar la sesión system_health</span><span class="sxs-lookup"><span data-stu-id="275b1-131">Restoring the system_health Session</span></span>  
 <span data-ttu-id="275b1-132">Si elimina la sesión system_health, puede restaurarla si ejecuta el archivo **u_tables.sql** en el Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="275b1-132">If you delete the system_health session, you can restore it by executing the **u_tables.sql** file in Query Editor.</span></span> <span data-ttu-id="275b1-133">Este archivo se encuentra en la siguiente carpeta, donde C: representa la unidad en la que se instalaron los archivos de programa de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="275b1-133">This file is located in the following folder, where C: represents the drive where you installed the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] program files:</span></span>  
  
 <span data-ttu-id="275b1-134">C:\Archivos de Programa\microsoft SQL Server\MSSQL12. \<*instanceid*> \MSSQL\Install</span><span class="sxs-lookup"><span data-stu-id="275b1-134">C:\Program Files\Microsoft SQL Server\MSSQL12.\<*instanceid*>\MSSQL\Install</span></span>  
  
 <span data-ttu-id="275b1-135">Tenga en cuenta que después de restaurar la sesión, debe iniciarla utilizando la instrucción ALTER EVENT SESSION o utilizando el nodo **Eventos extendidos** en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="275b1-135">Be aware that after you restore the session, you must start the session by using the ALTER EVENT SESSION statement or by using the **Extended Events** node in Object Explorer.</span></span> <span data-ttu-id="275b1-136">De lo contrario, la sesión se iniciará automáticamente la próxima vez que se reinicie el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="275b1-136">Otherwise, the session starts automatically the next time that you restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="275b1-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="275b1-137">See Also</span></span>  
 [<span data-ttu-id="275b1-138">Herramientas de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="275b1-138">Extended Events Tools</span></span>](extended-events-tools.md)  
  
  
