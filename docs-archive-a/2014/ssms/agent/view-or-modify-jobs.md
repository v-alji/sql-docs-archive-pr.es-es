---
title: Ver o modificar trabajos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], modifying
- jobs [SQL Server Agent], viewing
- modifying jobs
- viewing jobs
- SQL Server Agent jobs, viewing
- SQL Server Agent jobs, modifying
- displaying jobs
ms.assetid: 57f649b8-190c-4304-abd7-7ca5297deab7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5d0d731d25c20597be3ac84adfacd8973e4a51cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745608"
---
# <a name="view-or-modify-jobs"></a><span data-ttu-id="f72b5-102">Ver o modificar trabajos</span><span class="sxs-lookup"><span data-stu-id="f72b5-102">View or Modify Jobs</span></span>
  <span data-ttu-id="f72b5-103">Puede ver cualquier trabajo que haya creado.</span><span class="sxs-lookup"><span data-stu-id="f72b5-103">You can view any job you have created.</span></span> <span data-ttu-id="f72b5-104">Asimismo, después de ejecutar un trabajo, puede ver su historial.</span><span class="sxs-lookup"><span data-stu-id="f72b5-104">After you have run a job, you can also view its history.</span></span> <span data-ttu-id="f72b5-105">El historial de un trabajo le permite ver cuándo se ejecutó el trabajo, el estado del trabajo en conjunto y el estado de cada paso del trabajo.</span><span class="sxs-lookup"><span data-stu-id="f72b5-105">Viewing a job's history allows you to see when the job ran, the status of the job as a whole, and the status of each job step in the job.</span></span> <span data-ttu-id="f72b5-106">Puede ver si el trabajo ha tenido algún error en el pasado, cuándo finalizó correctamente por última vez y qué salida ha creado el trabajo cada vez que se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="f72b5-106">You can see whether the job ever failed in the past, when the job last completed successfully, and what output the job created each time the job ran.</span></span> <span data-ttu-id="f72b5-107">Los miembros del rol fijo de servidor **sysadmin** pueden ver o modificar cualquier trabajo, con independencia de quién sea el propietario.</span><span class="sxs-lookup"><span data-stu-id="f72b5-107">Members of the **sysadmin** fixed server role can view or modify any job, regardless of the owner.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f72b5-108">Para que exista un historial de trabajos, éste debe haberse ejecutado al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="f72b5-108">A job must have been executed at least one time for there to be a job history.</span></span> <span data-ttu-id="f72b5-109">Puede limitar el tamaño total del registro de historial de trabajos y el tamaño por trabajo.</span><span class="sxs-lookup"><span data-stu-id="f72b5-109">You can limit the total size of the job history log and the size per job.</span></span>  
  
 <span data-ttu-id="f72b5-110">Por último, puede modificar un trabajo para satisfacer nuevos requisitos.</span><span class="sxs-lookup"><span data-stu-id="f72b5-110">Finally, you can modify a job to meet new requirements.</span></span> <span data-ttu-id="f72b5-111">Puede modificar:</span><span class="sxs-lookup"><span data-stu-id="f72b5-111">You can modify:</span></span>  
  
-   <span data-ttu-id="f72b5-112">Opciones de respuesta</span><span class="sxs-lookup"><span data-stu-id="f72b5-112">Response options</span></span>  
  
-   <span data-ttu-id="f72b5-113">Programaciones</span><span class="sxs-lookup"><span data-stu-id="f72b5-113">Schedules</span></span>  
  
-   <span data-ttu-id="f72b5-114">Pasos de trabajo</span><span class="sxs-lookup"><span data-stu-id="f72b5-114">Job steps</span></span>  
  
-   <span data-ttu-id="f72b5-115">Propiedad</span><span class="sxs-lookup"><span data-stu-id="f72b5-115">Ownership</span></span>  
  
-   <span data-ttu-id="f72b5-116">Categoría de trabajo</span><span class="sxs-lookup"><span data-stu-id="f72b5-116">Job category</span></span>  
  
-   <span data-ttu-id="f72b5-117">Servidores de destino (solo para trabajos multiservidor)</span><span class="sxs-lookup"><span data-stu-id="f72b5-117">Target servers (multiserver jobs only)</span></span>  
  
 <span data-ttu-id="f72b5-118">Para asegurarse de que los cambios en los trabajos multiservidor surten efecto, debe exponer los cambios en la lista de descarga con el fin de que los servidores de destino puedan descargar el trabajo actualizado.</span><span class="sxs-lookup"><span data-stu-id="f72b5-118">To make sure that changes to multiserver jobs take effect, you must post the changes to the download list so that target servers can download the updated job.</span></span> <span data-ttu-id="f72b5-119">Para asegurarse de que los servidores de destino tienen las definiciones de trabajos más actuales, exponga una instrucción INSERT después de actualizar el trabajo multiservidor, de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="f72b5-119">To ensure that target servers have the most current job definitions, post an INSERT instruction after you update the multiserver job as follows:</span></span>  
  
```  
EXECUTE sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="f72b5-120">Para obtener más información, vea [sp_purge_jobhistory &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f72b5-120">For more information, see [sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql).</span></span>  
  
 <span data-ttu-id="f72b5-121">Los miembros del rol fijo de servidor **sysadmin** pueden ver la definición o el historial de cualquier trabajo, y pueden modificar cualquier trabajo.</span><span class="sxs-lookup"><span data-stu-id="f72b5-121">Members of the **sysadmin** fixed server role can view the definition or history of any job, and can modify any job.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f72b5-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f72b5-122">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f72b5-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f72b5-123">**Description**</span></span>|<span data-ttu-id="f72b5-124">**Tema.**</span><span class="sxs-lookup"><span data-stu-id="f72b5-124">**Topic**</span></span>|  
|<span data-ttu-id="f72b5-125">Describe cómo ver trabajos del Agente [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f72b5-125">Describes how to view [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="f72b5-126">View a Job</span><span class="sxs-lookup"><span data-stu-id="f72b5-126">View a Job</span></span>](view-a-job.md)|  
|<span data-ttu-id="f72b5-127">Describe cómo ver el registro del historial de trabajos del Agente [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f72b5-127">Describes how to view the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="f72b5-128">Ver el historial de trabajos</span><span class="sxs-lookup"><span data-stu-id="f72b5-128">View the Job History</span></span>](view-the-job-history.md)|  
|<span data-ttu-id="f72b5-129">Describe cómo eliminar el contenido del registro del historial de trabajos del Agente [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f72b5-129">Describes how to delete the contents of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="f72b5-130">Clear the Job History Log</span><span class="sxs-lookup"><span data-stu-id="f72b5-130">Clear the Job History Log</span></span>](clear-the-job-history-log.md)|  
|<span data-ttu-id="f72b5-131">Describe cómo establecer límites de tamaño para los registros de historial de trabajos del Agente [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f72b5-131">Describes how to set size limits for [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history logs.</span></span>|[<span data-ttu-id="f72b5-132">Resize the Job History Log</span><span class="sxs-lookup"><span data-stu-id="f72b5-132">Resize the Job History Log</span></span>](resize-the-job-history-log.md)|  
|<span data-ttu-id="f72b5-133">Describe cómo cambiar las propiedades de los trabajos del Agente [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f72b5-133">Describes how to change the properties of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="f72b5-134">Modify a Job</span><span class="sxs-lookup"><span data-stu-id="f72b5-134">Modify a Job</span></span>](modify-a-job.md)|  
  
## <a name="see-also"></a><span data-ttu-id="f72b5-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f72b5-135">See Also</span></span>  
 [<span data-ttu-id="f72b5-136">dbo.sysjobhistory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f72b5-136">dbo.sysjobhistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysjobhistory-transact-sql)  
  
  
