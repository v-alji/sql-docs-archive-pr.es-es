---
title: Implementar trabajos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent]
- SQL Server Agent jobs
- SQL Server Agent jobs, about jobs
- jobs [SQL Server Agent], about jobs
ms.assetid: 69e06724-25c7-4fb3-8a5b-3d4596f21756
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1925b3113db8d7c57ac4344958c0247763cfd1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662471"
---
# <a name="implement-jobs"></a><span data-ttu-id="9a7f4-102">Implementar trabajos</span><span class="sxs-lookup"><span data-stu-id="9a7f4-102">Implement Jobs</span></span>
  <span data-ttu-id="9a7f4-103">Puede utilizar los trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para automatizar tareas administrativas rutinarias y ejecutarlas periódicamente, lo que permite que la administración sea más eficaz.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-103">You can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to automate routine administrative tasks and run them on a recurring basis, making administration more efficient.</span></span>  
  
 <span data-ttu-id="9a7f4-104">Un trabajo es una serie específica de operaciones que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] realiza secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-104">A job is a specified series of operations performed sequentially by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="9a7f4-105">Un trabajo puede realizar una amplia variedad de actividades, incluidos scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] , aplicaciones de línea de comandos, scripts de Microsoft ActiveX, paquetes de Integration Services, comandos y consultas de Analysis Services o tareas de replicación.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-105">A job can perform a wide range of activities, including running [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, command-line applications, Microsoft ActiveX scripts, Integration Services packages, Analysis Services commands and queries, or Replication tasks.</span></span> <span data-ttu-id="9a7f4-106">Los trabajos pueden ejecutar tareas repetitivas o que se pueden programar y pueden notificar automáticamente a los usuarios el estado del trabajo mediante alertas, simplificando mucho la administración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a7f4-106">Jobs can run repetitive tasks or those that can be scheduled, and they can automatically notify users of job status by generating alerts, thereby greatly simplifying [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administration.</span></span>  
  
 <span data-ttu-id="9a7f4-107">Puede ejecutar los trabajos manualmente o configurarlos para que se ejecuten de acuerdo con una programación o en respuesta a alertas.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-107">You can run a job manually, or you can configure it to run according to a schedule or in response to alerts.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="9a7f4-108">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="9a7f4-108">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9a7f4-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9a7f4-109">**Description**</span></span>|<span data-ttu-id="9a7f4-110">**Tema.**</span><span class="sxs-lookup"><span data-stu-id="9a7f4-110">**Topic**</span></span>|  
|<span data-ttu-id="9a7f4-111">Contiene información sobre cómo crear trabajos y asignar su propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-111">Contains information about creating jobs and assigning ownership.</span></span>|[<span data-ttu-id="9a7f4-112">Crear trabajos</span><span class="sxs-lookup"><span data-stu-id="9a7f4-112">Create Jobs</span></span>](create-jobs.md)|  
|<span data-ttu-id="9a7f4-113">Contiene información sobre cómo organizar trabajos en categorías.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-113">Contains information about organizing jobs into categories.</span></span>|[<span data-ttu-id="9a7f4-114">organizar los trabajos</span><span class="sxs-lookup"><span data-stu-id="9a7f4-114">Organize Jobs</span></span>](organize-jobs.md)|  
|<span data-ttu-id="9a7f4-115">Contiene información acerca de los diferentes tipos de pasos de trabajo que puede crear y cómo administrarlos.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-115">Contains information about the different kinds of job steps you can create and how to manage them.</span></span>|[<span data-ttu-id="9a7f4-116">Administrar pasos de trabajo</span><span class="sxs-lookup"><span data-stu-id="9a7f4-116">Manage Job Steps</span></span>](manage-job-steps.md)|  
|<span data-ttu-id="9a7f4-117">Contiene información acerca de cómo definir cuándo se iniciarán los trabajos que se ejecutan y la frecuencia con la que deben ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-117">Contains information about how to define when jobs start running and how often they should run.</span></span>|[<span data-ttu-id="9a7f4-118">Crear y adjuntar programaciones a trabajos</span><span class="sxs-lookup"><span data-stu-id="9a7f4-118">Create and Attach Schedules to Jobs</span></span>](create-and-attach-schedules-to-jobs.md)|  
|<span data-ttu-id="9a7f4-119">Contiene información acerca de la ejecución manual de trabajos (sin una programación).</span><span class="sxs-lookup"><span data-stu-id="9a7f4-119">Contains information about manually running jobs (without a schedule).</span></span>|[<span data-ttu-id="9a7f4-120">Ejecutar trabajos</span><span class="sxs-lookup"><span data-stu-id="9a7f4-120">Run Jobs</span></span>](run-jobs.md)|  
|<span data-ttu-id="9a7f4-121">Contiene información acerca de cómo se puede configurar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que responda a los trabajos.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-121">Contains information about how you can configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to respond to jobs.</span></span> <span data-ttu-id="9a7f4-122">Por ejemplo, se puede configurar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que notifique a los administradores cuándo finalicen los trabajos.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-122">For example, you can configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to notify administrators when jobs are finished.</span></span>|[<span data-ttu-id="9a7f4-123">Especificar respuestas de trabajos</span><span class="sxs-lookup"><span data-stu-id="9a7f4-123">Specify Job Responses</span></span>](specify-job-responses.md)|  
|<span data-ttu-id="9a7f4-124">Contiene información acerca de cómo ver los trabajos existentes, su historial cuando se han ejecutado y cómo modificarlos.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-124">Contains information about how to view existing jobs, their history once executes, and how to modify them.</span></span>|[<span data-ttu-id="9a7f4-125">Ver o modificar trabajos</span><span class="sxs-lookup"><span data-stu-id="9a7f4-125">View or Modify Jobs</span></span>](view-or-modify-jobs.md)|  
|<span data-ttu-id="9a7f4-126">Contiene información acerca de cómo eliminar trabajos.</span><span class="sxs-lookup"><span data-stu-id="9a7f4-126">Contains information about how to delete jobs.</span></span>|[<span data-ttu-id="9a7f4-127">eliminar trabajos</span><span class="sxs-lookup"><span data-stu-id="9a7f4-127">Delete Jobs</span></span>](delete-jobs.md)|  
  
## <a name="see-also"></a><span data-ttu-id="9a7f4-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a7f4-128">See Also</span></span>  
 [<span data-ttu-id="9a7f4-129">Implementar la seguridad del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="9a7f4-129">Implement SQL Server Agent Security</span></span>](implement-sql-server-agent-security.md)  
  
  
