---
title: Supervisar la actividad de trabajos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, monitoring
- jobs [SQL Server Agent], monitoring
- monitoring [SQL Server], jobs
- activity monitoring [SQL Server Agent]
- monitoring [SQL Server], SQL Server Agent
- monitoring [SQL Server Agent]
- SQL Server Agent Job Activity Monitor
- SQL Server Agent jobs, monitoring
- performance [SQL Server], jobs
- current activity
ms.assetid: 71cb432b-631d-4b8b-9965-e731b3d8266d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5088e029e90b4556c1559f8c948e8a8734762749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671329"
---
# <a name="monitor-job-activity"></a><span data-ttu-id="c179e-102">Actividad de trabajos de monitor</span><span class="sxs-lookup"><span data-stu-id="c179e-102">Monitor Job Activity</span></span>
  <span data-ttu-id="c179e-103">Puede supervisar la actividad actual de todos los trabajos definidos de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante el Monitor de actividad de trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c179e-103">You can monitor the current activity of all defined jobs on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job Activity Monitor.</span></span>  
  
## <a name="sql-server-agent-sessions"></a><span data-ttu-id="c179e-104">Sesiones del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="c179e-104">SQL Server Agent Sessions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c179e-105">El Agente crea una sesión cada vez que se inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="c179e-105">Agent creates a new session each time the service starts.</span></span> <span data-ttu-id="c179e-106">Al crear una sesión, la tabla **sysjobactivity** de la base de datos **msdb** se rellena con todos los trabajos definidos existentes.</span><span class="sxs-lookup"><span data-stu-id="c179e-106">When a new session is created, the **sysjobactivity** table in the **msdb** database is populated with all the existing defined jobs.</span></span> <span data-ttu-id="c179e-107">Esta tabla mantiene la última actividad para los trabajos cuando se reinicia el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c179e-107">This table preserves the last activity for jobs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is restarted.</span></span> <span data-ttu-id="c179e-108">Cada sesión registra la actividad de trabajo normal del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde el inicio del trabajo hasta que termina.</span><span class="sxs-lookup"><span data-stu-id="c179e-108">Each session records [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent normal job activity from the start of the job to its finish.</span></span> <span data-ttu-id="c179e-109">La información acerca de estas sesiones se almacena en la tabla **syssessions** de la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="c179e-109">Information about these sessions is stored in the **syssessions** table of the **msdb** database.</span></span>  
  
## <a name="job-activity-monitor"></a><span data-ttu-id="c179e-110">Monitor de actividad de trabajo</span><span class="sxs-lookup"><span data-stu-id="c179e-110">Job Activity Monitor</span></span>  
 <span data-ttu-id="c179e-111">El Monitor de actividad de trabajo permite ver la tabla **sysjobactivity** mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c179e-111">The Job Activity Monitor allows you to view the **sysjobactivity** table by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="c179e-112">Puede ver todos los trabajos del servidor, o bien puede definir filtros para limitar el número de trabajos mostrados.</span><span class="sxs-lookup"><span data-stu-id="c179e-112">You can view all jobs on the server, or you can define filters to limit the number of jobs displayed.</span></span> <span data-ttu-id="c179e-113">También puede ordenar la información sobre los trabajos haciendo clic en un encabezado de columna de la cuadrícula **Actividad de trabajo del agente** .</span><span class="sxs-lookup"><span data-stu-id="c179e-113">You can also sort the job information by clicking on a column heading in the **Agent Job Activity** grid.</span></span> <span data-ttu-id="c179e-114">Por ejemplo, al seleccionar el encabezado de columna **Última ejecución** , puede ver los trabajos en el orden en que se ejecutaron por última vez.</span><span class="sxs-lookup"><span data-stu-id="c179e-114">For example, when you select the **Last Run** column heading, you can view the jobs in the order that they were last run.</span></span> <span data-ttu-id="c179e-115">Al volver a hacer clic en el encabezado de columna, el orden de los trabajos cambia entre ascendente y descendente basándose en la fecha en que se ejecutaron por última vez.</span><span class="sxs-lookup"><span data-stu-id="c179e-115">Clicking the column heading again toggles the jobs in ascending and descending order based on their last run date.</span></span>  
  
 <span data-ttu-id="c179e-116">El Monitor de actividad de trabajo le permite realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="c179e-116">Using the Job Activity Monitor you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="c179e-117">Iniciar y detener trabajos.</span><span class="sxs-lookup"><span data-stu-id="c179e-117">Start and stop jobs.</span></span>  
  
-   <span data-ttu-id="c179e-118">Ver las propiedades del trabajo.</span><span class="sxs-lookup"><span data-stu-id="c179e-118">View job properties.</span></span>  
  
-   <span data-ttu-id="c179e-119">Ver el historial de un determinado trabajo.</span><span class="sxs-lookup"><span data-stu-id="c179e-119">View the history for a specific job.</span></span>  
  
-   <span data-ttu-id="c179e-120">Actualizar la información de la cuadrícula **Actividad de trabajo del agente** manualmente o establecer un intervalo de actualización automático haciendo clic en **Ver configuración de actualización**.</span><span class="sxs-lookup"><span data-stu-id="c179e-120">Refresh the information in the **Agent Job Activity** grid manually or set an automatic refresh interval by clicking **View refresh settings**.</span></span>  
  
 <span data-ttu-id="c179e-121">Utilice el Monitor de actividad de trabajo cuando desee localizar los trabajos que están programados para su ejecución, el último resultado de los trabajos que se han ejecutado durante la sesión actual y localizar los trabajos que se están ejecutando actualmente o que están inactivos.</span><span class="sxs-lookup"><span data-stu-id="c179e-121">Use the Job Activity Monitor when you want to find out what jobs are scheduled to run, the last outcome of jobs that have run during the current session, and to find out which jobs are currently running or idle.</span></span> <span data-ttu-id="c179e-122">Si el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiene un error inesperado, puede determinar los trabajos que se estaban ejecutando buscando en la sesión anterior del Monitor de actividad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c179e-122">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service fails unexpectedly, you can determine which jobs were in the middle of being executed by looking at the previous session in the Job Activity Monitor.</span></span>  
  
 <span data-ttu-id="c179e-123">Para abrir el Monitor de actividad de trabajo, expanda **Agente SQL Server** en el Explorador de objetos de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , haga clic con el botón derecho en **Monitor de actividad de trabajo**y haga clic en **Ver actividad de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="c179e-123">To open the Job Activity Monitor, expand **SQL Server Agent** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Object Explorer, right-click **Job Activity Monitor**, and click **View Job Activity**.</span></span>  
  
 <span data-ttu-id="c179e-124">También puede ver la actividad de trabajo de la sesión actual mediante el procedimiento almacenado **sp_help_jobactivity**.</span><span class="sxs-lookup"><span data-stu-id="c179e-124">You can also view job activity for the current session by using the stored procedure **sp_help_jobactivity**.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c179e-125">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c179e-125">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c179e-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c179e-126">**Description**</span></span>|<span data-ttu-id="c179e-127">**Tema.**</span><span class="sxs-lookup"><span data-stu-id="c179e-127">**Topic**</span></span>|  
|<span data-ttu-id="c179e-128">Describe cómo ver el estado de tiempo de ejecución de los trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c179e-128">Describes how to view the runtime state of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="c179e-129">Ver actividad de trabajo</span><span class="sxs-lookup"><span data-stu-id="c179e-129">View Job Activity</span></span>](view-job-activity.md)|  
  
## <a name="see-also"></a><span data-ttu-id="c179e-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c179e-130">See Also</span></span>  
 <span data-ttu-id="c179e-131">[Ver la actividad de trabajo](view-job-activity.md) </span><span class="sxs-lookup"><span data-stu-id="c179e-131">[View Job Activity](view-job-activity.md) </span></span>  
 <span data-ttu-id="c179e-132">[dbo.sysjobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-sysjobactivity-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c179e-132">[dbo.sysjobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-sysjobactivity-transact-sql) </span></span>  
 <span data-ttu-id="c179e-133">[Sesiones dedbo.sys&#40;&#41;de Transact-SQL](/sql/relational-databases/system-tables/dbo-syssessions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c179e-133">[dbo.syssessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-syssessions-transact-sql) </span></span>  
 [<span data-ttu-id="c179e-134">sp_help_jobactivity &#40;&#41;de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c179e-134">sp_help_jobactivity &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql)  
  
  
