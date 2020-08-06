---
title: Tarea Ejecutar trabajo del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqlserveragentjobtask.f1
helpviewer_keywords:
- Execute SQL Server Agent Job task [Integration Services]
- jobs [Integration Services]
- SQL Server Agent [Integration Services]
ms.assetid: 3aa3bc0e-1a1c-452e-81b8-b4e3422ea053
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d0c66eb7022312fa3ec3d161f63a9aee92b840f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673835"
---
# <a name="execute-sql-server-agent-job-task"></a><span data-ttu-id="77265-102">Tarea Ejecutar trabajo del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="77265-102">Execute SQL Server Agent Job Task</span></span>
  <span data-ttu-id="77265-103">La tarea Ejecutar trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ejecuta trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77265-103">The Execute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job task runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="77265-104">es un servicio de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows que ejecuta trabajos definidos en una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77265-104">Agent is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows service that runs jobs that have been defined in an instance of SQL Server.</span></span> <span data-ttu-id="77265-105">Puede crear trabajos que ejecuten instrucciones de Transact-SQL y scripts de ActiveX, realizar tareas de mantenimiento de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y Replicación, o ejecutar paquetes.</span><span class="sxs-lookup"><span data-stu-id="77265-105">You can create jobs that execute Transact-SQL statements and ActiveX scripts, perform [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and Replication maintenance tasks, or run packages.</span></span> <span data-ttu-id="77265-106">También puede configurar un trabajo para supervisar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y activar alertas.</span><span class="sxs-lookup"><span data-stu-id="77265-106">You can also configure a job to monitor [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and fire alerts.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="77265-107">generalmente se utilizan para automatizar tareas que se realizan con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="77265-107">Agent jobs are typically used to automate tasks that you perform repeatedly.</span></span> <span data-ttu-id="77265-108">Para más información, vea [Implementar trabajos](../../ssms/agent/implement-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="77265-108">For more information, see [Implement Jobs](../../ssms/agent/implement-jobs.md).</span></span>  
  
 <span data-ttu-id="77265-109">Un paquete puede utilizar la tarea Ejecutar trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para realizar tareas administrativas relacionadas con componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77265-109">By using the Execute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job task, a package can perform administrative tasks related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="77265-110">Por ejemplo, un trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede ejecutar un procedimiento almacenado del sistema, como **sp_enum_dtspackages** , para obtener una lista de paquetes de una carpeta.</span><span class="sxs-lookup"><span data-stu-id="77265-110">For example, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job can run a system stored procedure such as **sp_enum_dtspackages** to obtain a list of packages in a folder.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77265-111">El Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe estar ejecutándose para poder ejecutar automáticamente trabajos administrativos locales o multiservidor.</span><span class="sxs-lookup"><span data-stu-id="77265-111">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be running before local or multiserver administrative jobs can run automatically.</span></span>  
  
 <span data-ttu-id="77265-112">Esta tarea encapsula el procedimiento del sistema **sp_start_job** y pasa el nombre del trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] al procedimiento como un argumento.</span><span class="sxs-lookup"><span data-stu-id="77265-112">This task encapsulates the **sp_start_job** system procedure and passes the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job to the procedure as an argument.</span></span> <span data-ttu-id="77265-113">Para más información, vea [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="77265-113">For more information, see [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span></span>  
  
## <a name="configuring-the-execute-sql-server-agent-job-task"></a><span data-ttu-id="77265-114">Configurar la tarea Ejecutar trabajo del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="77265-114">Configuring the Execute SQL Server Agent Job Task</span></span>  
 <span data-ttu-id="77265-115">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77265-115">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="77265-116">Esta tarea se encuentra en la sección **Tareas del plan de mantenimiento** del **Cuadro de herramientas** , en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77265-116">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="77265-117">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="77265-117">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="77265-118">Tarea Ejecutar trabajo del Agente SQL Server &#40;Plan de mantenimiento&#41;</span><span class="sxs-lookup"><span data-stu-id="77265-118">Execute SQL Server Agent Job Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/execute-sql-server-agent-job-task-maintenance-plan.md)  
  
 <span data-ttu-id="77265-119">Para obtener más información sobre cómo establecer estas propiedades en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="77265-119">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="77265-120">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="77265-120">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
