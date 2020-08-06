---
title: Programar un trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- scheduling jobs [SQL Server]
- SQL Server Agent jobs, scheduling
- jobs [SQL Server Agent], scheduling
ms.assetid: f626390a-a3df-4970-b7a7-a0529e4a109c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1077766d6853ed7c029b8eefa76515c89ad861fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745620"
---
# <a name="schedule-a-job"></a><span data-ttu-id="94275-102">Schedule a Job</span><span class="sxs-lookup"><span data-stu-id="94275-102">Schedule a Job</span></span>
  <span data-ttu-id="94275-103">En este tema se describe cómo programar un trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94275-103">This topic describes how to schedule a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
-   <span data-ttu-id="94275-104">**Antes de empezar:** ,</span><span class="sxs-lookup"><span data-stu-id="94275-104">**Before you begin:** ,</span></span>  
  
     [<span data-ttu-id="94275-105">Seguridad</span><span class="sxs-lookup"><span data-stu-id="94275-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="94275-106">**Para programar un trabajo, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="94275-106">**To schedule a job, using:**</span></span>  
  
     [<span data-ttu-id="94275-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="94275-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="94275-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="94275-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="94275-109">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="94275-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="94275-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="94275-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="94275-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="94275-111">Security</span></span>  
 <span data-ttu-id="94275-112">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="94275-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="94275-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="94275-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-and-attach-a-schedule-to-a-job"></a><span data-ttu-id="94275-114">Para crear y asociar una programación a un trabajo</span><span class="sxs-lookup"><span data-stu-id="94275-114">To create and attach a schedule to a job</span></span>  
  
1.  <span data-ttu-id="94275-115">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="94275-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="94275-116">Expanda **Agente SQL Server**, expanda **Trabajos**, haga clic con el botón derecho en el trabajo que desee programar y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="94275-116">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to schedule, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="94275-117">Seleccione la página **Programaciones** y, a continuación, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="94275-117">Select the **Schedules** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="94275-118">En el cuadro **Nombre** , escriba el nombre de la nueva programación.</span><span class="sxs-lookup"><span data-stu-id="94275-118">In the **Name** box, type a name for the new schedule.</span></span>  
  
5.  <span data-ttu-id="94275-119">Desactive la casilla **Habilitado** si no desea que la programación tenga efecto inmediatamente después de su creación.</span><span class="sxs-lookup"><span data-stu-id="94275-119">Clear the **Enabled** check box if you do not want the schedule to take effect immediately following its creation.</span></span>  
  
6.  <span data-ttu-id="94275-120">En **Tipo de programación**, seleccione una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="94275-120">For **Schedule Type**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="94275-121">Haga clic en **Iniciar automáticamente al iniciar el Agente SQL Server** para iniciar el trabajo cuando se inicie el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94275-121">Click **Start automatically when SQL Server Agent starts** to start the job when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is started.</span></span>  
  
    -   <span data-ttu-id="94275-122">Haga clic en **Iniciar al quedar inactivas las CPU** para iniciar el trabajo cuando las CPU alcancen la condición de inactivas.</span><span class="sxs-lookup"><span data-stu-id="94275-122">Click **Start whenever the CPUs become idle** to start the job when the CPUs reach an idle condition.</span></span>  
  
    -   <span data-ttu-id="94275-123">Haga clic en **Periódica** si desea que una programación se ejecute varias veces.</span><span class="sxs-lookup"><span data-stu-id="94275-123">Click **Recurring** if you want a schedule to run repeatedly.</span></span> <span data-ttu-id="94275-124">Para establecer la programación periódica, rellene los grupos **Frecuencia**, **Frecuencia diaria**y **Duración** en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="94275-124">To set the recurring schedule, complete the **Frequency**, **Daily Frequency**, and **Duration** groups on the dialog.</span></span>  
  
    -   <span data-ttu-id="94275-125">Haga clic en **Una vez** si desea que la programación se ejecute solo una vez.</span><span class="sxs-lookup"><span data-stu-id="94275-125">Click **One time** if you want the schedule to run only once.</span></span> <span data-ttu-id="94275-126">Para establecer la programación en **Una vez** , rellene el grupo **Repetición una vez** del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="94275-126">To set the **One time** schedule, complete the **One-time occurrence** group on the dialog.</span></span>  
  
#### <a name="to-attach-a-schedule-to-a-job"></a><span data-ttu-id="94275-127">Para asociar una programación a un trabajo</span><span class="sxs-lookup"><span data-stu-id="94275-127">To attach a schedule to a job</span></span>  
  
1.  <span data-ttu-id="94275-128">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="94275-128">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="94275-129">Expanda **Agente SQL Server**y **Trabajos**, haga clic con el botón derecho en el trabajo que desee programar, y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="94275-129">Expand **SQL Server Agent**, expand **Jobs**, right-click the job that you want to schedule, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="94275-130">Seleccione la página **Programaciones** y, a continuación, haga clic en **Elegir**.</span><span class="sxs-lookup"><span data-stu-id="94275-130">Select the **Schedules** page, and then click **Pick**.</span></span>  
  
4.  <span data-ttu-id="94275-131">Seleccione la programación que desee asociar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="94275-131">Select the schedule that you want to attach, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="94275-132">En el cuadro de diálogo **Propiedades del trabajo** , haga doble clic en la programación asociada.</span><span class="sxs-lookup"><span data-stu-id="94275-132">In the **Job Properties** dialog box, double-click the attached schedule.</span></span>  
  
6.  <span data-ttu-id="94275-133">Compruebe que **Fecha de inicio** se ha establecido correctamente.</span><span class="sxs-lookup"><span data-stu-id="94275-133">Verify that **Start date** is set correctly.</span></span> <span data-ttu-id="94275-134">Si no es así, establezca la fecha en el valor que desee para que la programación se inicie y, a continuación, hace clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="94275-134">If it is not, set the date when you want for the schedule to start, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="94275-135">En el cuadro de diálogo **Propiedades del trabajo** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="94275-135">In the **Job Properties** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="94275-136">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="94275-136">Using Transact-SQL</span></span>  
  
#### <a name="to-schedule-a-job"></a><span data-ttu-id="94275-137">Para programar un trabajo</span><span class="sxs-lookup"><span data-stu-id="94275-137">To schedule a job</span></span>  
  
1.  <span data-ttu-id="94275-138">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94275-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="94275-139">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="94275-139">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="94275-140">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="94275-140">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
    -- creates a schedule named NightlyJobs.   
    -- Jobs that use this schedule execute every day when the time on the server is 01:00.   
    EXEC sp_add_schedule  
        @schedule_name = N'NightlyJobs' ,  
        @freq_type = 4,  
        @freq_interval = 1,  
        @active_start_time = 010000 ;  
    GO  
    -- attaches the schedule to the job BackupDatabase  
    EXEC sp_attach_schedule  
       @job_name = N'BackupDatabase',  
       @schedule_name = N'NightlyJobs' ;  
    GO  
    ```  
  
 <span data-ttu-id="94275-141">Para obtener más información, vea [sp_add_schedule &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql) y [sp_attach_schedule &#40;transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="94275-141">For more information, see [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql) and [sp_attach_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="94275-142">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="94275-142">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="94275-143">Utilice la clase `JobSchedule` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94275-143">Use the `JobSchedule` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="94275-144">Para más información, consulte[Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="94275-144">For more information, see[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
