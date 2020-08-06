---
title: Crear trabajos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], creating
- SQL Server Agent jobs, creating
ms.assetid: 465fb7fc-7622-4252-a178-ea51691c935b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 706b9348eed5b190f99543a74e7019dc1bde5978
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745642"
---
# <a name="create-jobs"></a><span data-ttu-id="57e9a-102">Crear trabajos</span><span class="sxs-lookup"><span data-stu-id="57e9a-102">Create Jobs</span></span>
  <span data-ttu-id="57e9a-103">Un trabajo es una serie específica de operaciones que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] realiza secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="57e9a-103">A job is a specified series of operations performed sequentially by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="57e9a-104">Un trabajo puede realizar una amplia variedad de actividades, incluidos scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] , aplicaciones de símbolo del sistema, scripts de Microsoft ActiveX, paquetes de Integration Services, comandos y consultas de Analysis Services o tareas de replicación.</span><span class="sxs-lookup"><span data-stu-id="57e9a-104">A job can perform a wide range of activities, including running [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, command prompt applications, Microsoft ActiveX scripts, Integration Services packages, Analysis Services commands and queries, or Replication tasks.</span></span> <span data-ttu-id="57e9a-105">Los trabajos pueden ejecutar tareas repetitivas o que se pueden programar, y pueden notificar automáticamente a los usuarios el estado del trabajo mediante alertas, lo cual simplifica en gran medida la administración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="57e9a-105">Jobs can run repetitive or schedulable tasks, and they can automatically notify users of job status by generating alerts, thereby greatly simplifying [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administration.</span></span>  
  
 <span data-ttu-id="57e9a-106">Para crear un trabajo, el usuario debe ser miembro de uno de los roles fijos de base de datos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="57e9a-106">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="57e9a-107">Solo pueden editar el trabajo el propietario de éste o los miembros del rol **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="57e9a-107">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="57e9a-108">Los miembros del rol **sysadmin** pueden asignar el valor de propiedad de trabajo a otros usuarios, y pueden ejecutar cualquier trabajo, independientemente del propietario del trabajo.</span><span class="sxs-lookup"><span data-stu-id="57e9a-108">Members of the **sysadmin** role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span> <span data-ttu-id="57e9a-109">Para más información sobre los roles fijos de base de datos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte [Roles fijos de base de datos del Agente SQL Server](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="57e9a-109">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="57e9a-110">Se puede escribir un trabajo para que se ejecute en la instancia local de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o en varias instancias de una empresa.</span><span class="sxs-lookup"><span data-stu-id="57e9a-110">Jobs can be written to run on the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or on multiple instances across an enterprise.</span></span> <span data-ttu-id="57e9a-111">Para ejecutar trabajos en varios servidores, debe configurar al menos un servidor maestro, y uno o más servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="57e9a-111">To run jobs on multiple servers, you must set up at least one master server and one or more target servers.</span></span> <span data-ttu-id="57e9a-112">Para más información sobre los servidores maestros y de destino, consulte [Administración automatizada en una empresa](automated-administration-across-an-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="57e9a-112">For more information about master and target servers, see [Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md)</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="57e9a-113">El Agente registra la información del trabajo y de los pasos de trabajo en el historial de trabajos.</span><span class="sxs-lookup"><span data-stu-id="57e9a-113">Agent records job and job step information in the job history.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="57e9a-114">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="57e9a-114">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57e9a-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="57e9a-115">**Description**</span></span>|<span data-ttu-id="57e9a-116">**Tema.**</span><span class="sxs-lookup"><span data-stu-id="57e9a-116">**Topic**</span></span>|  
|<span data-ttu-id="57e9a-117">Describe cómo crear un trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="57e9a-117">Describes how to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="57e9a-118">Crear un trabajo</span><span class="sxs-lookup"><span data-stu-id="57e9a-118">Create a Job</span></span>](create-a-job.md)|  
|<span data-ttu-id="57e9a-119">Describe cómo volver a asignar a otro usuario la propiedad de los trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="57e9a-119">Describes how to reassign ownership of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to another user.</span></span>|[<span data-ttu-id="57e9a-120">Give Others Ownership of a Job</span><span class="sxs-lookup"><span data-stu-id="57e9a-120">Give Others Ownership of a Job</span></span>](give-others-ownership-of-a-job.md)|  
|<span data-ttu-id="57e9a-121">Describe cómo configurar el registro de historial de trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="57e9a-121">Describes how to set up the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="57e9a-122">Set Up the Job History Log</span><span class="sxs-lookup"><span data-stu-id="57e9a-122">Set Up the Job History Log</span></span>](set-up-the-job-history-log.md)|  
  
## <a name="see-also"></a><span data-ttu-id="57e9a-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57e9a-123">See Also</span></span>  
 <span data-ttu-id="57e9a-124">[Administrar pasos de trabajo](manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="57e9a-124">[Manage Job Steps](manage-job-steps.md) </span></span>  
 <span data-ttu-id="57e9a-125">[Administración automatizada en una empresa](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="57e9a-125">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 <span data-ttu-id="57e9a-126">[Crear y adjuntar programaciones a trabajos](create-and-attach-schedules-to-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="57e9a-126">[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md) </span></span>  
 <span data-ttu-id="57e9a-127">[Ejecutar trabajos](run-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="57e9a-127">[Run Jobs](run-jobs.md) </span></span>  
 [<span data-ttu-id="57e9a-128">Ver o modificar trabajos</span><span class="sxs-lookup"><span data-stu-id="57e9a-128">View or Modify Jobs</span></span>](view-or-modify-jobs.md)  
  
  
