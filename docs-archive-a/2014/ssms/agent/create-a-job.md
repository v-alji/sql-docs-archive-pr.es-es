---
title: Crear un trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], creating
- SQL Server Agent jobs, creating
ms.assetid: b35af2b6-6594-40d1-9861-4d5dd906048c
author: stevestein
ms.author: sstein
ms.openlocfilehash: de74f032924fbb0b6643bd8f3d482481ffb1f983
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662486"
---
# <a name="create-a-job"></a><span data-ttu-id="f674e-102">Creación de un trabajo</span><span class="sxs-lookup"><span data-stu-id="f674e-102">Create a Job</span></span>
  <span data-ttu-id="f674e-103">En este tema se describe cómo crear un trabajo del Agente SQL Server en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] u Objetos de administración de SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="f674e-103">This topic describes how to create a SQL Server Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="f674e-104">Para agregar pasos de trabajo, programas, alertas y notificaciones que puedan enviarse a los operadores, vea los vínculos a los temas de la sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="f674e-104">To add job steps, schedules, alerts, and notifications that can be sent to operators, see the links to topics in the See Also section.</span></span>  
  
-   <span data-ttu-id="f674e-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f674e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f674e-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f674e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f674e-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f674e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f674e-108">**Para crear un trabajo, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="f674e-108">**To create a job, using:**</span></span>  
  
     <span data-ttu-id="f674e-109">[SQL Server Management Studio](#SSMSProcedure),</span><span class="sxs-lookup"><span data-stu-id="f674e-109">[SQL Server Management Studio](#SSMSProcedure),</span></span>  
  
     [<span data-ttu-id="f674e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f674e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="f674e-111">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f674e-111">SQL Server Management Objects</span></span>](#SMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f674e-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f674e-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f674e-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f674e-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f674e-114">Para crear un trabajo, el usuario debe ser miembro de uno de los roles fijos de base de datos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="f674e-114">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="f674e-115">Solo pueden editar el trabajo el propietario de éste o los miembros del rol **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="f674e-115">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="f674e-116">Para más información sobre los roles fijos de base de datos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte [Roles fijos de base de datos del Agente SQL Server](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f674e-116">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
-   <span data-ttu-id="f674e-117">La asignación de un trabajo a otro inicio de sesión no garantiza que el nuevo propietario disponga de los permisos suficientes para ejecutar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f674e-117">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
-   <span data-ttu-id="f674e-118">El Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] local almacena los trabajos locales en la caché.</span><span class="sxs-lookup"><span data-stu-id="f674e-118">Local jobs are cached by the local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="f674e-119">Por lo tanto, cualquier modificación obliga implícitamente al Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a volver a almacenar el trabajo en la caché.</span><span class="sxs-lookup"><span data-stu-id="f674e-119">Therefore, any modifications implicitly force [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to re-cache the job.</span></span> <span data-ttu-id="f674e-120">Puesto que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no almacena el trabajo en la caché hasta que se llama a **sp_add_jobserver** , resulta más eficaz llamar a **sp_add_jobserver** al final.</span><span class="sxs-lookup"><span data-stu-id="f674e-120">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent does not cache the job until **sp_add_jobserver** is called, it is more efficient to call **sp_add_jobserver** last.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f674e-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f674e-121">Security</span></span>  
  
-   <span data-ttu-id="f674e-122">Para cambiar el propietario de un trabajo debe ser administrador de sistema.</span><span class="sxs-lookup"><span data-stu-id="f674e-122">You must be a system administrator to change the owner of a job.</span></span>  
  
-   <span data-ttu-id="f674e-123">Por razones de seguridad, solo el propietario del trabajo o un miembro del rol **sysadmin** puede cambiar la definición del trabajo.</span><span class="sxs-lookup"><span data-stu-id="f674e-123">For security reasons, only the job owner or a member of the **sysadmin** role can change the definition of the job.</span></span> <span data-ttu-id="f674e-124">Solo los miembros del rol fijo de servidor **sysadmin** pueden asignar la propiedad de un trabajo a otros usuarios y pueden ejecutar cualquier trabajo, independientemente de quién sea el propietario del mismo.</span><span class="sxs-lookup"><span data-stu-id="f674e-124">Only members of the **sysadmin** fixed server role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f674e-125">Si cambia la propiedad de un trabajo a un usuario que no es miembro del rol fijo de servidor **sysadmin** y el trabajo está ejecutando unos pasos que necesitan las cuentas de un servidor proxy (por ejemplo, la ejecución de paquetes [!INCLUDE[ssIS](../../includes/ssis-md.md)] ), asegúrese de que el usuario tenga acceso a ese servidor proxy o, de lo contrario, se producirán errores en el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f674e-125">If you change job ownership to a user who is not a member of the **sysadmin** fixed server role, and the job is executing job steps that require proxy accounts (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] package execution), make sure that the user has access to that proxy account or else the job will fail.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f674e-126">Permisos</span><span class="sxs-lookup"><span data-stu-id="f674e-126">Permissions</span></span>  
 <span data-ttu-id="f674e-127">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="f674e-127">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f674e-128">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f674e-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="f674e-129">Para crear un trabajo del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="f674e-129">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="f674e-130">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en el que desea crear un trabajo del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f674e-130">In the **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent job.</span></span>  
  
2.  <span data-ttu-id="f674e-131">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f674e-131">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="f674e-132">Haga clic con el botón derecho en la carpeta **Trabajos** y, después, seleccione **Nuevo trabajo...**.</span><span class="sxs-lookup"><span data-stu-id="f674e-132">Right-click the **Jobs** folder and select **New Job...**.</span></span>  
  
4.  <span data-ttu-id="f674e-133">En el cuadro de diálogo **Nuevo trabajo** , en la página **General** , modifique las propiedades generales del trabajo.</span><span class="sxs-lookup"><span data-stu-id="f674e-133">In the **New Job** dialog box, on the **General** page, modify the general properties of the job.</span></span> <span data-ttu-id="f674e-134">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo y nuevo trabajo &#40;página General&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span><span class="sxs-lookup"><span data-stu-id="f674e-134">For more information on the available options on this page, see [Job Properties and New Job &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span></span>  
  
5.  <span data-ttu-id="f674e-135">En la página **Pasos** , organice los pasos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f674e-135">On the **Steps** page, organize the job steps.</span></span> <span data-ttu-id="f674e-136">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo: nuevo trabajo &#40;página pasos&#41;](job-properties-new-job-steps-page.md)</span><span class="sxs-lookup"><span data-stu-id="f674e-136">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](job-properties-new-job-steps-page.md)</span></span>  
  
6.  <span data-ttu-id="f674e-137">En la página **Programaciones** , organice las programaciones del trabajo.</span><span class="sxs-lookup"><span data-stu-id="f674e-137">On the **Schedules** page, organize schedules for the job.</span></span> <span data-ttu-id="f674e-138">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo: nueva página programaciones de &#40;de trabajos&#41;](job-properties-new-job-schedules-page.md)</span><span class="sxs-lookup"><span data-stu-id="f674e-138">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md)</span></span>  
  
7.  <span data-ttu-id="f674e-139">En la página **Alertas** , organice las alertas del trabajo.</span><span class="sxs-lookup"><span data-stu-id="f674e-139">On the **Alerts** page, organize the alerts for the job.</span></span> <span data-ttu-id="f674e-140">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo: nueva página de alertas de &#40;de trabajo&#41;](job-properties-new-job-alerts-page.md)</span><span class="sxs-lookup"><span data-stu-id="f674e-140">For more information on the available options on this page, see [Job Properties: New Job &#40;Alerts Page&#41;](job-properties-new-job-alerts-page.md)</span></span>  
  
8.  <span data-ttu-id="f674e-141">En la página **Notificaciones**, establezca las acciones que el Agente [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe realizar cuando se complete el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f674e-141">On the **Notifications** page, set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span> <span data-ttu-id="f674e-142">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo: nueva página de notificaciones de &#40;de trabajo&#41;](job-properties-new-job-notifications-page.md).</span><span class="sxs-lookup"><span data-stu-id="f674e-142">For more information on the available options on this page, see [Job Properties: New Job &#40;Notifications Page&#41;](job-properties-new-job-notifications-page.md).</span></span>  
  
9. <span data-ttu-id="f674e-143">En la página **Destinos** , administre los servidores de destino del trabajo.</span><span class="sxs-lookup"><span data-stu-id="f674e-143">On the **Targets** page, manage the target servers for the job.</span></span> <span data-ttu-id="f674e-144">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo: nuevo trabajo &#40;página destinos&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="f674e-144">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
10. <span data-ttu-id="f674e-145">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f674e-145">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f674e-146">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f674e-146">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="f674e-147">Para crear un trabajo del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="f674e-147">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="f674e-148">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f674e-148">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f674e-149">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f674e-149">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f674e-150">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f674e-150">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_job  
        @job_name = N'Weekly Sales Data Backup' ;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
    USE msdb ;  
    GO  
    EXEC sp_attach_schedule  
       @job_name = N'Weekly Sales Data Backup',  
       @schedule_name = N'RunOnce';  
    GO  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Data Backup';  
    GO  
    ```  
  
 <span data-ttu-id="f674e-151">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f674e-151">For more information, see:</span></span>  
  
-   [<span data-ttu-id="f674e-152">sp_add_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f674e-152">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="f674e-153">sp_add_jobstep &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f674e-153">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="f674e-154">sp_add_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f674e-154">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="f674e-155">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f674e-155">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="f674e-156">sp_add_jobserver &#40;&#41;de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f674e-156">sp_add_jobserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMOProcedure"></a><span data-ttu-id="f674e-157">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f674e-157">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="f674e-158">**Para crear un trabajo del Agente SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f674e-158">**To create a SQL Server Agent job**</span></span>  
  
 <span data-ttu-id="f674e-159">Llame al método `Create` de la clase `Job` mediante el lenguaje de programación que desee, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f674e-159">Call the `Create` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="f674e-160">Para el código de ejemplo, consulte [Programar tareas administrativas automáticas en el Agente SQL Server](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="f674e-160">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
  
##  <a name="SSMSProc2"></a>  
