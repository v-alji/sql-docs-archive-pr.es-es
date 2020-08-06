---
title: Monitor de actividad de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.ACTIVITYMON.F1
- sql12.ag.jobactivitymonitor.alljobs.f1
ms.assetid: 11f2182c-5f71-46f8-8d2b-74f0fc48f2d6
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6f89d5448f0885c85229c2808ee6f85bf6fa071
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745635"
---
# <a name="job-activity-monitor"></a><span data-ttu-id="8b055-102">Monitor de actividad de trabajo</span><span class="sxs-lookup"><span data-stu-id="8b055-102">Job Activity Monitor</span></span>
  <span data-ttu-id="8b055-103">Utilice esta página para ver la actividad actual de los trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8b055-103">Use this page to view the current activity of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span> <span data-ttu-id="8b055-104">Haga clic en **Filtro** para limitar el número de trabajos mostrados.</span><span class="sxs-lookup"><span data-stu-id="8b055-104">Click **Filter** to limit the jobs displayed.</span></span> <span data-ttu-id="8b055-105">La cuadrícula **Actividad de trabajo del agente** es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="8b055-105">The **Agent Job Activity** grid is read-only.</span></span> <span data-ttu-id="8b055-106">Haga clic en los encabezados de columna para ordenar la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="8b055-106">Click on the column headers to sort the grid.</span></span> <span data-ttu-id="8b055-107">Si desea modificar un trabajo, haga doble clic en el trabajo para abrir el cuadro de diálogo **Propiedades del trabajo** .</span><span class="sxs-lookup"><span data-stu-id="8b055-107">To modify a job, double-click the job to open the **Job Properties** dialog box.</span></span> <span data-ttu-id="8b055-108">Haga clic con el botón secundario en un trabajo de la cuadrícula para que comiencen a ejecutarse todos los pasos del trabajo, para iniciar un paso del trabajo determinado, deshabilitar o habilitar el trabajo, actualizarlo, eliminarlo, ver su historial o ver sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="8b055-108">Right-click a job in the grid to start it running all job steps, start at a particular job step, disable or enable the job, refresh the job, delete the job, view the history of the job, or view the properties of the job.</span></span> <span data-ttu-id="8b055-109">Haga clic en **Actualizar** para actualizar la cuadrícula con información actual.</span><span class="sxs-lookup"><span data-stu-id="8b055-109">Click **Refresh** to update the grid with current information.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8b055-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="8b055-110">Options</span></span>  
 <span data-ttu-id="8b055-111">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="8b055-111">**Name**</span></span>  
 <span data-ttu-id="8b055-112">Nombre del trabajo.</span><span class="sxs-lookup"><span data-stu-id="8b055-112">Name of the job.</span></span>  
  
 <span data-ttu-id="8b055-113">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="8b055-113">**Enabled**</span></span>  
 <span data-ttu-id="8b055-114">Indica si el trabajo está habilitado (**sí**) o no (**no**).</span><span class="sxs-lookup"><span data-stu-id="8b055-114">Whether the job is enabled (**yes**) or not enabled (**no**).</span></span>  
  
 <span data-ttu-id="8b055-115">**Estado** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8b055-115">**Status** <sup>1</sup></span></span>  
 <span data-ttu-id="8b055-116">Estado actual del trabajo.</span><span class="sxs-lookup"><span data-stu-id="8b055-116">Current status of the job.</span></span>  
  
 <span data-ttu-id="8b055-117">**Resultado de la última ejecución**</span><span class="sxs-lookup"><span data-stu-id="8b055-117">**Last Run Outcome**</span></span>  
 <span data-ttu-id="8b055-118">Estado del trabajo cuando se ejecutó por última vez.</span><span class="sxs-lookup"><span data-stu-id="8b055-118">Job status when last run.</span></span>  
  
 <span data-ttu-id="8b055-119">**Última ejecución**</span><span class="sxs-lookup"><span data-stu-id="8b055-119">**Last Run**</span></span>  
 <span data-ttu-id="8b055-120">Fecha y hora en que se ejecutó el trabajo por última vez con la fecha y hora locales del servidor.</span><span class="sxs-lookup"><span data-stu-id="8b055-120">Date and time job was last run using the local date and time of the server.</span></span>  
  
 <span data-ttu-id="8b055-121">**Siguiente ejecución** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8b055-121">**Next Run** <sup>1</sup></span></span>  
 <span data-ttu-id="8b055-122">Fecha y hora en que se ha programado la próxima ejecución del trabajo con la fecha y hora locales del servidor.</span><span class="sxs-lookup"><span data-stu-id="8b055-122">Date and time the job is next scheduled to run using the local date and time of the server.</span></span>  
  
 <span data-ttu-id="8b055-123">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="8b055-123">**Category**</span></span>  
 <span data-ttu-id="8b055-124">Categoría asignada al trabajo.</span><span class="sxs-lookup"><span data-stu-id="8b055-124">The job category assigned to the job.</span></span>  
  
 <span data-ttu-id="8b055-125">**Xterm**</span><span class="sxs-lookup"><span data-stu-id="8b055-125">**Runnable**</span></span>  
 <span data-ttu-id="8b055-126">**Sí** si el trabajo puede ejecutarse; **No** si el trabajo no puede ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="8b055-126">**Yes** if the job can be run; **No** if the job cannot be run.</span></span> <span data-ttu-id="8b055-127">No puede ejecutarse un trabajo que no disponga de pasos o de un servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="8b055-127">A job is not runnable if it has no steps or if it has no target server.</span></span>  
  
 <span data-ttu-id="8b055-128">**Programado**</span><span class="sxs-lookup"><span data-stu-id="8b055-128">**Scheduled**</span></span>  
 <span data-ttu-id="8b055-129">**Sí** si se ha asignado el trabajo a una programación de trabajo; **No** si el trabajo no tiene ninguna programación.</span><span class="sxs-lookup"><span data-stu-id="8b055-129">**Yes** if the job is assigned to a job schedule; **No** if the job has no schedule.</span></span>  
  
 <span data-ttu-id="8b055-130"><sup>1</sup> Solo los miembros del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rol fijo de servidor sysadmin y del grupo administradores de servidor pueden ver los valores de esta columna.</span><span class="sxs-lookup"><span data-stu-id="8b055-130"><sup>1</sup>Only members of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sysadmin fixed server role and the server administrators group can see values in this column.</span></span> <span data-ttu-id="8b055-131">Los miembros del rol SQLAgentOperatorRole no pueden ver los valores en esta columna.</span><span class="sxs-lookup"><span data-stu-id="8b055-131">Members of the SQLAgentOperatorRole role cannot see values in this column.</span></span>  
  
#### <a name="to-open-the-job-activity-monitor"></a><span data-ttu-id="8b055-132">Para abrir el Monitor de actividad de trabajo</span><span class="sxs-lookup"><span data-stu-id="8b055-132">To open the Job Activity Monitor</span></span>  
  
-   <span data-ttu-id="8b055-133">En el **Explorador de objetos**, expanda su servidor, expanda **Agente SQL Server**, haga clic con el botón derecho en **Monitor de actividad de trabajo**y, luego, haga clic en **Ver actividad de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="8b055-133">In **Object Explorer**, expand your server, expand **SQL Server Agent**, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b055-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b055-134">See Also</span></span>  
 [<span data-ttu-id="8b055-135">Actividad de trabajos de monitor</span><span class="sxs-lookup"><span data-stu-id="8b055-135">Monitor Job Activity</span></span>](monitor-job-activity.md)  
  
  
