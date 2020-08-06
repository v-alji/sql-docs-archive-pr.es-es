---
title: Crear y adjuntar programaciones a trabajos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server]
- scheduling jobs [SQL Server]
- jobs [SQL Server], scheduling
- CPU [SQL Server], idle conditions
- automatic job processing
- SQL Server Agent jobs, scheduling
- idle time [SQL Server]
ms.assetid: 079c2984-0052-4a37-a2b8-4ece56e6b6b5
author: stevestein
ms.author: sstein
ms.openlocfilehash: ced47013b6552725e6350b113a3722b066016a6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745648"
---
# <a name="create-and-attach-schedules-to-jobs"></a><span data-ttu-id="4bc01-102">Crear y adjuntar programaciones a trabajos</span><span class="sxs-lookup"><span data-stu-id="4bc01-102">Create and Attach Schedules to Jobs</span></span>
  <span data-ttu-id="4bc01-103">La programación de trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consiste en definir las condiciones que provocan el inicio de la ejecución de los trabajos sin intervención del usuario.</span><span class="sxs-lookup"><span data-stu-id="4bc01-103">Scheduling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs means defining the condition or conditions that cause the job to begin running without user interaction.</span></span> <span data-ttu-id="4bc01-104">Puede programar que un trabajo se ejecute automáticamente creando una nueva programación para el trabajo, o adjuntando una programación existente al trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bc01-104">You can schedule a job to run automatically by creating a new schedule for the job, or by attaching an existing schedule to the job.</span></span>  
  
 <span data-ttu-id="4bc01-105">Hay dos maneras de crear una programación:</span><span class="sxs-lookup"><span data-stu-id="4bc01-105">There are two ways to create a schedule:</span></span>  
  
-   <span data-ttu-id="4bc01-106">Crear la programación mientras se está creando un trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bc01-106">Create the schedule while you are creating a job.</span></span>  
  
-   <span data-ttu-id="4bc01-107">Crear la programación en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="4bc01-107">Create the schedule in Object Explorer.</span></span>  
  
 <span data-ttu-id="4bc01-108">Una vez creada una programación, puede adjuntarla a varios trabajos, aun cuando la programación se haya creado para un trabajo concreto.</span><span class="sxs-lookup"><span data-stu-id="4bc01-108">After a schedule has been created, you can attach that schedule to multiple jobs, even if the schedule was created for a specific job.</span></span> <span data-ttu-id="4bc01-109">También puede separar las programaciones de los trabajos.</span><span class="sxs-lookup"><span data-stu-id="4bc01-109">You can also detach schedules from jobs.</span></span>  
  
 <span data-ttu-id="4bc01-110">Una programación puede basarse en tiempo o en un evento.</span><span class="sxs-lookup"><span data-stu-id="4bc01-110">A schedule can be based upon time or an event.</span></span> <span data-ttu-id="4bc01-111">Por ejemplo, puede programar un trabajo para que se ejecute en los momentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4bc01-111">For example, you can schedule a job to run at the following times:</span></span>  
  
-   <span data-ttu-id="4bc01-112">Cuando se inicia el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bc01-112">Whenever [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent starts.</span></span>  
  
-   <span data-ttu-id="4bc01-113">Cuando el uso de la CPU del equipo se encuentre en un nivel que se haya definido como inactivo.</span><span class="sxs-lookup"><span data-stu-id="4bc01-113">Whenever CPU utilization of the computer is at a level you have defined as idle.</span></span>  
  
-   <span data-ttu-id="4bc01-114">Una vez, a una hora y una fecha específicas.</span><span class="sxs-lookup"><span data-stu-id="4bc01-114">One time, at a specific date and time.</span></span>  
  
-   <span data-ttu-id="4bc01-115">Según una programación periódica.</span><span class="sxs-lookup"><span data-stu-id="4bc01-115">On a recurring schedule.</span></span>  
  
 <span data-ttu-id="4bc01-116">Como alternativa a las programaciones de trabajo, también puede crear una alerta que responda a un evento ejecutando un trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bc01-116">As an alternative to job schedules, you can also create an alert that responds to an event by running a job.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4bc01-117">Solo se puede ejecutar una instancia del trabajo cada vez.</span><span class="sxs-lookup"><span data-stu-id="4bc01-117">Only one instance of the job can be run at a time.</span></span> <span data-ttu-id="4bc01-118">Si intenta ejecutar un trabajo manualmente mientras se está ejecutando en el momento programado, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rechazará la solicitud.</span><span class="sxs-lookup"><span data-stu-id="4bc01-118">If you try to run a job manually while it is running as scheduled, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent refuses the request.</span></span>  
  
 <span data-ttu-id="4bc01-119">Para impedir que un trabajo programado se ejecute, debe realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="4bc01-119">To prevent a scheduled job from running, you must do one of the following:</span></span>  
  
-   <span data-ttu-id="4bc01-120">Deshabilitar la programación.</span><span class="sxs-lookup"><span data-stu-id="4bc01-120">Disable the schedule.</span></span>  
  
-   <span data-ttu-id="4bc01-121">Deshabilitar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bc01-121">Disable the job.</span></span>  
  
-   <span data-ttu-id="4bc01-122">Separar la programación del trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bc01-122">Detach the schedule from the job.</span></span>  
  
-   <span data-ttu-id="4bc01-123">Detener el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bc01-123">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
-   <span data-ttu-id="4bc01-124">Eliminar la programación.</span><span class="sxs-lookup"><span data-stu-id="4bc01-124">Delete the schedule.</span></span>  
  
 <span data-ttu-id="4bc01-125">Aunque no esté habilitada la programación, se puede ejecutar el trabajo en respuesta a una alerta o cuando un usuario lo ejecute manualmente.</span><span class="sxs-lookup"><span data-stu-id="4bc01-125">If the schedule is not enabled, the job can still run in response to an alert or when a user runs the job manually.</span></span> <span data-ttu-id="4bc01-126">Si no está habilitada una programación de trabajo, no estará habilitada para ningún trabajo que la utilice.</span><span class="sxs-lookup"><span data-stu-id="4bc01-126">When a job schedule is not enabled, the schedule is not enabled for any job that uses the schedule.</span></span>  
  
 <span data-ttu-id="4bc01-127">Las programaciones deshabilitadas se deben volver a habilitar de manera explícita.</span><span class="sxs-lookup"><span data-stu-id="4bc01-127">You must explicitly re-enable a schedule that has been disabled.</span></span> <span data-ttu-id="4bc01-128">La modificación de una programación no la vuelve a habilitar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4bc01-128">Editing the schedule does not automatically re-enable the schedule.</span></span>  
  
## <a name="scheduling-start-dates"></a><span data-ttu-id="4bc01-129">Programar fechas de inicio</span><span class="sxs-lookup"><span data-stu-id="4bc01-129">Scheduling Start Dates</span></span>  
 <span data-ttu-id="4bc01-130">La fecha de inicio de una programación debe ser mayor o igual que 19900101.</span><span class="sxs-lookup"><span data-stu-id="4bc01-130">The start date of a schedule must be greater than or equal to 19900101.</span></span>  
  
 <span data-ttu-id="4bc01-131">Al adjuntar una programación a un trabajo, se debe revisar la fecha de inicio que usa la programación para ejecutar por primera vez el trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bc01-131">When you are attaching a schedule to a job, you should review the start date that the schedule uses to run the job for the first time.</span></span> <span data-ttu-id="4bc01-132">La fecha de inicio depende del día y la hora en que se adjunte la programación al trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bc01-132">The start date depends upon the day and time when you attach the schedule to the job.</span></span> <span data-ttu-id="4bc01-133">Por ejemplo, si se crea una programación que se ejecuta cada dos lunes a las 8:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="4bc01-133">For example, you create a schedule that runs every other Monday at 8:00 A.M.</span></span> <span data-ttu-id="4bc01-134">Si se crea un trabajo a las 10:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="4bc01-134">If you create a job at 10:00 A.M.</span></span> <span data-ttu-id="4bc01-135">del lunes 3 de marzo de 2008, la fecha de inicio de la programación será lunes 17 de marzo de 2008.</span><span class="sxs-lookup"><span data-stu-id="4bc01-135">on Monday, March 3, 2008, the schedule start date is Monday, March 17, 2008.</span></span> <span data-ttu-id="4bc01-136">Si se crea otro trabajo el martes 4 de marzo de 2008, la fecha de inicio de la programación será lunes 10 de marzo de 2008.</span><span class="sxs-lookup"><span data-stu-id="4bc01-136">If you create another job on Tuesday, March 4, 2008, the schedule start date is Monday, March 10, 2008.</span></span>  
  
 <span data-ttu-id="4bc01-137">Puede cambiar la fecha de inicio de la programación después de adjuntar la programación a un trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bc01-137">You can change the schedule start date after you attach the schedule to a job.</span></span>  
  
## <a name="cpu-idle-schedules"></a><span data-ttu-id="4bc01-138">Programaciones de inactividad de CPU</span><span class="sxs-lookup"><span data-stu-id="4bc01-138">CPU Idle Schedules</span></span>  
 <span data-ttu-id="4bc01-139">Para maximizar los recursos de CPU, puede definir una condición de CPU inactiva para el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bc01-139">To maximize CPU resources, you can define a CPU idle condition for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4bc01-140">El Agente usa la configuración de la condición de CPU inactiva para determinar el momento más conveniente para ejecutar trabajos.</span><span class="sxs-lookup"><span data-stu-id="4bc01-140">Agent uses the CPU idle condition setting to determine the best time to run jobs.</span></span> <span data-ttu-id="4bc01-141">Por ejemplo, puede programar la ejecución de un trabajo de generación de índices durante el tiempo de inactividad de CPU y en periodos de baja producción.</span><span class="sxs-lookup"><span data-stu-id="4bc01-141">For example, you can schedule a job to rebuild indexes during CPU idle time and slow production periods.</span></span>  
  
 <span data-ttu-id="4bc01-142">Antes de definir trabajos para que se ejecuten durante el tiempo de inactividad de CPU, determine la carga de la CPU durante el procesamiento normal.</span><span class="sxs-lookup"><span data-stu-id="4bc01-142">Before you define jobs to run during CPU idle time, determine the load on the CPU during normal processing.</span></span> <span data-ttu-id="4bc01-143">Para ello, utilice el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] o el Monitor de rendimiento para supervisar el tráfico del servidor y obtener estadísticas.</span><span class="sxs-lookup"><span data-stu-id="4bc01-143">To do this, use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor to monitor server traffic and collect statistics.</span></span> <span data-ttu-id="4bc01-144">La información que obtenga puede utilizarla para establecer el porcentaje y la duración del tiempo de inactividad de CPU.</span><span class="sxs-lookup"><span data-stu-id="4bc01-144">You can then use the information you gather to set the CPU idle time percentage and duration.</span></span>  
  
 <span data-ttu-id="4bc01-145">Defina la condición de CPU inactiva como un porcentaje por debajo del cual el uso de CPU debe permanecer durante un intervalo de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="4bc01-145">Define the CPU idle condition as a percentage below which CPU usage must remain for a specified time.</span></span> <span data-ttu-id="4bc01-146">A continuación, establezca la duración.</span><span class="sxs-lookup"><span data-stu-id="4bc01-146">Next, set the amount of time.</span></span> <span data-ttu-id="4bc01-147">Cuando el uso de CPU esté por debajo del porcentaje especificado para el tiempo determinado, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] iniciará todos los trabajos que tengan una programación de tiempo de inactividad de CPU.</span><span class="sxs-lookup"><span data-stu-id="4bc01-147">When the CPU usage is below the specified percentage for the specified amount of time, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent starts all jobs that have a CPU idle time schedule.</span></span> <span data-ttu-id="4bc01-148">Para obtener más información sobre el uso de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] o el monitor de rendimiento para supervisar el uso de CPU, vea [supervisar el uso de CPU](../../relational-databases/performance-monitor/monitor-cpu-usage.md).</span><span class="sxs-lookup"><span data-stu-id="4bc01-148">For more information on using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor to monitor CPU usage, see [Monitor CPU Usage](../../relational-databases/performance-monitor/monitor-cpu-usage.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4bc01-149">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4bc01-149">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4bc01-150">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4bc01-150">**Description**</span></span>|<span data-ttu-id="4bc01-151">**Tema.**</span><span class="sxs-lookup"><span data-stu-id="4bc01-151">**Topic**</span></span>|  
|<span data-ttu-id="4bc01-152">Describe cómo crear una programación para un trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bc01-152">Describes how to create a schedule for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="4bc01-153">Crear una programación</span><span class="sxs-lookup"><span data-stu-id="4bc01-153">Create a Schedule</span></span>](create-a-schedule.md)|  
|<span data-ttu-id="4bc01-154">Describe cómo programar un trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bc01-154">Describes how to schedule a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="4bc01-155">Programar un trabajo</span><span class="sxs-lookup"><span data-stu-id="4bc01-155">Schedule a Job</span></span>](schedule-a-job.md)|  
|<span data-ttu-id="4bc01-156">Explica cómo definir la condición de inactividad de la CPU para el servidor.</span><span class="sxs-lookup"><span data-stu-id="4bc01-156">Explains how to define the CPU idle condition for your server.</span></span>|[<span data-ttu-id="4bc01-157">Establecer la duración y el tiempo de inactividad de la CPU &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc01-157">Set CPU Idle Time and Duration &#40;SQL Server Management Studio&#41;</span></span>](set-cpu-idle-time-and-duration-sql-server-management-studio.md)|  
  
## <a name="see-also"></a><span data-ttu-id="4bc01-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4bc01-158">See Also</span></span>  
 <span data-ttu-id="4bc01-159">[sp_help_jobschedule &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-help-jobschedule-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4bc01-159">[sp_help_jobschedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobschedule-transact-sql) </span></span>  
 [<span data-ttu-id="4bc01-160">dbo.sysjobschedules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc01-160">dbo.sysjobschedules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysjobschedules-transact-sql)  
  
  
