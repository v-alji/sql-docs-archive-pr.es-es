---
title: Eliminar trabajos | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- delete jobs
ms.assetid: bffb915e-bc84-4417-aa35-183243ca3312
author: stevestein
ms.author: sstein
ms.openlocfilehash: f66387a1334f91c29b8edddad293d76064430b39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748482"
---
# <a name="delete-jobs"></a><span data-ttu-id="8e214-102">eliminar trabajos</span><span class="sxs-lookup"><span data-stu-id="8e214-102">Delete Jobs</span></span>
  <span data-ttu-id="8e214-103">Un trabajo es una serie específica de operaciones que el Agente SQL Server realiza secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="8e214-103">A job is a specified series of operations performed sequentially by SQL Server Agent.</span></span> <span data-ttu-id="8e214-104">De forma predeterminada, los trabajos no se eliminan cuando finaliza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="8e214-104">By default, jobs are not deleted when execution finishes.</span></span> <span data-ttu-id="8e214-105">Puede eliminar uno o más trabajos del Agente [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] independientemente del éxito o del fracaso del trabajo.</span><span class="sxs-lookup"><span data-stu-id="8e214-105">You can delete one or more [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs regardless of success or failure of the job.</span></span> <span data-ttu-id="8e214-106">También puede configurar el Agente [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que elimine los trabajos automáticamente cuando se realizan correctamente, con error o se completan.</span><span class="sxs-lookup"><span data-stu-id="8e214-106">You can also configure [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically delete jobs when they succeed, fail, or complete.</span></span>  
  
 <span data-ttu-id="8e214-107">De forma predeterminada, los miembros del rol fijo de servidor **sysadmin** pueden ejecutar el sp_delete_job &#40;procedimiento almacenado del sistema [Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql) para eliminar un trabajo.</span><span class="sxs-lookup"><span data-stu-id="8e214-107">By default, members of the **sysadmin** fixed server role can execute the [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql) system stored procedure to delete a job.</span></span> <span data-ttu-id="8e214-108">Al resto de usuarios se les debe conceder uno de los siguientes roles fijos de base de datos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la base de datos **msdb** :</span><span class="sxs-lookup"><span data-stu-id="8e214-108">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="8e214-109">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="8e214-109">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="8e214-110">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="8e214-110">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="8e214-111">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="8e214-111">**SQLAgentOperatorRole**</span></span>  
  
 <span data-ttu-id="8e214-112">Para detalles sobre los permisos de estos roles, consulte [Roles fijos de base de datos del Agente SQL Server](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8e214-112">For details about the permissions of these roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="8e214-113">Los miembros del rol fijo de servidor **sysadmin** pueden ejecutar **sp_delete_job** para eliminar cualquier trabajo.</span><span class="sxs-lookup"><span data-stu-id="8e214-113">Members of the **sysadmin** fixed server role can execute **sp_delete_job** to delete any job.</span></span> <span data-ttu-id="8e214-114">Un usuario que no sea miembro del rol fijo de servidor **sysadmin** solo puede eliminar los trabajos de los que sea propietario.</span><span class="sxs-lookup"><span data-stu-id="8e214-114">A user that is not a member of the **sysadmin** fixed server role can only delete jobs owned by that user.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="8e214-115">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="8e214-115">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8e214-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8e214-116">**Description**</span></span>|<span data-ttu-id="8e214-117">**Tema.**</span><span class="sxs-lookup"><span data-stu-id="8e214-117">**Topic**</span></span>|  
|<span data-ttu-id="8e214-118">Describe cómo eliminar uno o varios de los trabajos del Agente [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e214-118">Describes how to delete one or more [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="8e214-119">Eliminar uno o más trabajos</span><span class="sxs-lookup"><span data-stu-id="8e214-119">Delete One or More Jobs</span></span>](delete-one-or-more-jobs.md)|  
|<span data-ttu-id="8e214-120">Describe cómo configurar el Agente [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que elimine los trabajos automáticamente cuando se realizan correctamente, con error o se completan.</span><span class="sxs-lookup"><span data-stu-id="8e214-120">Describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically delete jobs when they succeed, fail, or complete.</span></span>|[<span data-ttu-id="8e214-121">Automatically Delete a Job</span><span class="sxs-lookup"><span data-stu-id="8e214-121">Automatically Delete a Job</span></span>](automatically-delete-a-job.md)|  
  
  
