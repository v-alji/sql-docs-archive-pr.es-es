---
title: Creación de un plan de mantenimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- maintenance plans [SQL Server], creating
ms.assetid: a945cb65-ba7a-42f4-bbd9-6ec675745523
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3df0c1cd06427deb051a9c4214d03084b44c6f9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675355"
---
# <a name="create-a-maintenance-plan"></a><span data-ttu-id="2e151-102">Crear un plan de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="2e151-102">Create a Maintenance Plan</span></span>
  <span data-ttu-id="2e151-103">En este tema se describe cómo crear un plan de mantenimiento de un solo servidor o multiservidor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e151-103">This topic describes how to create a single server or multiserver maintenance plan in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2e151-104">Hay dos formas de crear estos planes de mantenimiento con [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]: con el Asistente para planes de mantenimiento o con la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="2e151-104">Using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], you can create these maintenance plans in one of two ways: by either using the Maintenance Plan Wizard or the design surface.</span></span> <span data-ttu-id="2e151-105">El uso del asistente es más conveniente si desea crear planes de mantenimiento básicos, mientras que la superficie de diseño le permite utilizar un flujo de trabajo mejorado.</span><span class="sxs-lookup"><span data-stu-id="2e151-105">The Wizard is best for creating basic maintenance plans, while creating a plan using the design surface allows you to utilize enhanced workflow.</span></span>  
  
 <span data-ttu-id="2e151-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="2e151-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2e151-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="2e151-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2e151-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="2e151-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2e151-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2e151-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2e151-110">**Para crear un plan de mantenimiento, usando:**</span><span class="sxs-lookup"><span data-stu-id="2e151-110">**To create a maintenance plan, using:**</span></span>  
  
     [<span data-ttu-id="2e151-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e151-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2e151-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2e151-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2e151-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="2e151-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2e151-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="2e151-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="2e151-115">Para crear un plan de mantenimiento multiservidor, se debe configurar un entorno multiservidor que contenga un servidor maestro y uno o varios servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="2e151-115">To create a multiserver maintenance plan, a multiserver environment containing one master server and one or more target servers must be configured.</span></span> <span data-ttu-id="2e151-116">Los planes de mantenimiento multiservidor se deben crear y mantener en el servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="2e151-116">Multiserver maintenance plans must be created and maintained on the master server.</span></span> <span data-ttu-id="2e151-117">Estos planes se pueden ver, pero no mantener, en servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="2e151-117">These plans can be viewed, but not maintained, on target servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2e151-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2e151-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2e151-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="2e151-119">Permissions</span></span>  
 <span data-ttu-id="2e151-120">Para crear o administrar planes de mantenimiento, debe ser miembro del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="2e151-120">To create or manage Maintenance Plans, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2e151-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e151-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-maintenance-plan-using-the-maintenance-plan-wizard"></a><span data-ttu-id="2e151-122">Para crear un plan de mantenimiento con el Asistente para planes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="2e151-122">To create a maintenance plan using the Maintenance Plan Wizard</span></span>  
  
1.  <span data-ttu-id="2e151-123">En el Explorador de objetos, haga clic en el signo más para expandir el servidor donde desea crear un plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="2e151-123">In Object Explorer, click the plus sign to expand the server where you want to create a maintenance plan.</span></span>  
  
2.  <span data-ttu-id="2e151-124">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="2e151-124">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="2e151-125">Haga clic con el botón derecho en la carpeta **Planes de mantenimiento** y seleccione **Asistente para planes de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="2e151-125">Right-click the **Maintenance Plans** folder and select **Maintenance Plan Wizard**.</span></span>  
  
4.  <span data-ttu-id="2e151-126">Siga los pasos del asistente para crear un plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="2e151-126">Follow the steps of the wizard to create a maintenance plan.</span></span> <span data-ttu-id="2e151-127">Para obtener más información, consulte [Use the Maintenance Plan Wizard](use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2e151-127">For more information, see [Use the Maintenance Plan Wizard](use-the-maintenance-plan-wizard.md).</span></span>  
  
#### <a name="to-create-a-maintenance-plan-using-the-design-surface"></a><span data-ttu-id="2e151-128">Para crear un plan de mantenimiento mediante la superficie de diseño</span><span class="sxs-lookup"><span data-stu-id="2e151-128">To create a maintenance plan using the design surface</span></span>  
  
1.  <span data-ttu-id="2e151-129">En el Explorador de objetos, haga clic en el signo más para expandir el servidor donde desea crear un plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="2e151-129">In Object Explorer, click the plus sign to expand the server where you want to create a maintenance plan.</span></span>  
  
2.  <span data-ttu-id="2e151-130">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="2e151-130">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="2e151-131">Haga clic con el botón derecho en la carpeta **Planes de mantenimiento** y seleccione **Nuevo plan de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="2e151-131">Right-click the **Maintenance Plans** folder and select **New Maintenance Plan**.</span></span>  
  
4.  <span data-ttu-id="2e151-132">Siga los pasos descritos en [Crear un plan de mantenimiento &#40;superficie de diseño del plan de mantenimiento&#41;](create-a-maintenance-plan-maintenance-plan-design-surface.md) para crear un plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="2e151-132">Create a maintenance plan following the steps in [Create a Maintenance Plan &#40;Maintenance Plan Design Surface&#41;](create-a-maintenance-plan-maintenance-plan-design-surface.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2e151-133">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2e151-133">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-maintenance-plan"></a><span data-ttu-id="2e151-134">Para crear un plan de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="2e151-134">To create a maintenance plan</span></span>  
  
1.  <span data-ttu-id="2e151-135">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e151-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2e151-136">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2e151-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2e151-137">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2e151-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    --  Adds a new job, executed by the SQL Server Agent service, called "HistoryCleanupTask_1".  
    EXEC dbo.sp_add_job  
       @job_name = N'HistoryCleanupTask_1',   
       @enabled = 1,   
       @description = N'Clean up old task history' ;   
    GO  
    -- Adds a job step for reorganizing all of the indexes in the HumanResources.Employee table to the HistoryCleanupTask_1 job.   
    EXEC dbo.sp_add_jobstep  
        @job_name = N'HistoryCleanupTask_1',   
        @step_name = N'Reorganize all indexes on HumanResources.Employee table',   
        @subsystem = N'TSQL',   
        @command = N'USE AdventureWorks2012  
    GO  
    ALTER INDEX AK_Employee_LoginID ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX AK_Employee_NationalIDNumber ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX AK_Employee_rowguid ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX IX_Employee_OrganizationNode ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    USE AdventureWorks2012  
    GO  
    ALTER INDEX PK_Employee_BusinessEntityID ON HumanResources.Employee REORGANIZE WITH ( LOB_COMPACTION = ON )   
    GO  
    ',   
        @retry_attempts = 5,   
        @retry_interval = 5 ;   
    GO  
    -- Creates a schedule named RunOnce that executes every day when the time on the server is 23:00.   
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',   
        @freq_type = 4,   
        @freq_interval = 1,   
        @active_start_time = 233000 ;   
    GO  
    -- Attaches the RunOnce schedule to the job HistoryCleanupTask_1.   
    EXEC sp_attach_schedule  
       @job_name = N'HistoryCleanupTask_1'  
       @schedule_name = N'RunOnce' ;   
    GO  
  
    ```  
  
 <span data-ttu-id="2e151-138">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="2e151-138">For more information, see:</span></span>  
  
-   [<span data-ttu-id="2e151-139">sp_add_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2e151-139">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="2e151-140">sp_add_jobstep &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2e151-140">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="2e151-141">sp_add_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2e151-141">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="2e151-142">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2e151-142">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
  
