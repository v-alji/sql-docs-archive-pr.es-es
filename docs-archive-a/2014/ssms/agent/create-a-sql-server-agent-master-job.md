---
title: Crear un trabajo maestro del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], master jobs
- jobs [SQL Server Agent], creating
- master SQL Server Agent job [SQL Server]
ms.assetid: c12ab23f-d7ee-43a5-8cd2-0a9121292bcd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8a6503caec3f153878e360ee29ce09a5c099ade5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746083"
---
# <a name="create-a-sql-server-agent-master-job"></a><span data-ttu-id="8bc60-102">Crear un trabajo maestro del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="8bc60-102">Create a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="8bc60-103">En este tema se describe cómo crear un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabajo del agente principal en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8bc60-103">This topic describes how to create a master [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8bc60-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="8bc60-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8bc60-105">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="8bc60-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="8bc60-106">Los cambios en los trabajos principales del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se deben transmitir a todos los servidores de destino implicados.</span><span class="sxs-lookup"><span data-stu-id="8bc60-106">Changes to master [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs must be propagated to all involved target servers.</span></span> <span data-ttu-id="8bc60-107">Dado que los servidores de destino no descargan inicialmente un trabajo hasta que se especifican dichos destinos, [!INCLUDE[msCoName](../../includes/msconame-md.md)] recomienda completar todos los pasos y programaciones de un trabajo concreto antes de especificar los servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="8bc60-107">Because target servers do not initially download a job until those targets are specified, [!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you complete all job steps and job schedules for a particular job before you specify any target servers.</span></span> <span data-ttu-id="8bc60-108">De lo contrario, debe solicitar manualmente que los servidores de destino vuelvan a descargar el trabajo modificado, ejecutando el procedimiento almacenado **sp_post_msx_operation** o modificando el trabajo mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bc60-108">Otherwise, you must manual request that the target servers download the modified job again, either by executing the **sp_post_msx_operation** stored procedure or modifying the job using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="8bc60-109">Para obtener más información, vea [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) o [modificar un trabajo](modify-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="8bc60-109">For more information, see [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) or [Modify a Job](modify-a-job.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8bc60-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8bc60-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8bc60-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="8bc60-111">Permissions</span></span>  
 <span data-ttu-id="8bc60-112">Los trabajos distribuidos que tienen pasos asociados a un proxy se ejecutan bajo el contexto de la cuenta de proxy en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="8bc60-112">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="8bc60-113">Para que se descarguen del servidor maestro al de destino los pasos de trabajo asociados con un proxy, asegúrese de que se cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8bc60-113">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="8bc60-114">La subclave del registro **\ HKEY_LOCAL_MACHINE \software\microsoft\microsoft SQL Server \\ < *instance_name*> \sql Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) está establecida en 1 (true).</span><span class="sxs-lookup"><span data-stu-id="8bc60-114">The registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="8bc60-115">De forma predeterminada, esta subclave está establecida en 0 (false).</span><span class="sxs-lookup"><span data-stu-id="8bc60-115">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="8bc60-116">Existe una cuenta de proxy en el servidor de destino que tiene el mismo nombre que la cuenta de proxy del servidor maestro bajo el que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bc60-116">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="8bc60-117">Si se producen errores en los pasos de trabajo que utilizan cuentas de proxy durante la descarga de éstos desde el servidor maestro al servidor de destino, puede buscar en la columna **error_message** de la tabla **sysdownloadlist** de la base de datos **msdb** los mensajes de error que digan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8bc60-117">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="8bc60-118">"Este trabajo requiere una cuenta de proxy, pero la coincidencia de proxy se ha deshabilitado en el servidor de destino."</span><span class="sxs-lookup"><span data-stu-id="8bc60-118">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span> <span data-ttu-id="8bc60-119">Para resolver este error, establezca la subclave de registro **AllowDownloadedJobsToMatchProxyName** en 1.</span><span class="sxs-lookup"><span data-stu-id="8bc60-119">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="8bc60-120">"No se encontró el proxy".</span><span class="sxs-lookup"><span data-stu-id="8bc60-120">"Proxy not found."</span></span> <span data-ttu-id="8bc60-121">Para resolver este error, asegúrese de que existe una cuenta de proxy en el servidor de destino con el mismo nombre que la cuenta de proxy del servidor maestro en la que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bc60-121">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8bc60-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8bc60-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-master-sql-server-agent-job"></a><span data-ttu-id="8bc60-123">Para crear un trabajo principal del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="8bc60-123">To create a master SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="8bc60-124">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en el que desea crear un trabajo del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8bc60-124">In the **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent job.</span></span>  
  
2.  <span data-ttu-id="8bc60-125">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8bc60-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="8bc60-126">Haga clic con el botón derecho en la carpeta **Trabajos** y, después, seleccione **Nuevo trabajo...**.</span><span class="sxs-lookup"><span data-stu-id="8bc60-126">Right-click the **Jobs** folder and select **New Job...**.</span></span>  
  
4.  <span data-ttu-id="8bc60-127">En el cuadro de diálogo **Nuevo trabajo** , en la página **General** , modifique las propiedades generales del trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bc60-127">In the **New Job** dialog box, on the **General** page, modify the general properties of the job.</span></span> <span data-ttu-id="8bc60-128">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo y nuevo trabajo &#40;página General&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span><span class="sxs-lookup"><span data-stu-id="8bc60-128">For more information on the available options on this page, see [Job Properties and New Job &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)</span></span>  
  
5.  <span data-ttu-id="8bc60-129">En la página **Pasos** , organice los pasos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bc60-129">On the **Steps** page, organize the job steps.</span></span> <span data-ttu-id="8bc60-130">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo: nuevo trabajo &#40;página pasos&#41;](job-properties-new-job-steps-page.md)</span><span class="sxs-lookup"><span data-stu-id="8bc60-130">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](job-properties-new-job-steps-page.md)</span></span>  
  
6.  <span data-ttu-id="8bc60-131">En la página **Programaciones** , organice las programaciones del trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bc60-131">On the **Schedules** page, organize schedules for the job.</span></span> <span data-ttu-id="8bc60-132">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo: nueva página programaciones de &#40;de trabajos&#41;](job-properties-new-job-schedules-page.md)</span><span class="sxs-lookup"><span data-stu-id="8bc60-132">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md)</span></span>  
  
7.  <span data-ttu-id="8bc60-133">En la página **Alertas** , organice las alertas del trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bc60-133">On the **Alerts** page, organize the alerts for the job.</span></span> <span data-ttu-id="8bc60-134">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo: nueva página de alertas de &#40;de trabajo&#41;](job-properties-new-job-alerts-page.md)</span><span class="sxs-lookup"><span data-stu-id="8bc60-134">For more information on the available options on this page, see [Job Properties: New Job &#40;Alerts Page&#41;](job-properties-new-job-alerts-page.md)</span></span>  
  
8.  <span data-ttu-id="8bc60-135">En la página **Notificaciones**, establezca las acciones que el Agente [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe realizar cuando se complete el trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bc60-135">On the **Notifications** page, set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span> <span data-ttu-id="8bc60-136">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo: nueva página de notificaciones de &#40;de trabajo&#41;](job-properties-new-job-notifications-page.md).</span><span class="sxs-lookup"><span data-stu-id="8bc60-136">For more information on the available options on this page, see [Job Properties: New Job &#40;Notifications Page&#41;](job-properties-new-job-notifications-page.md).</span></span>  
  
9. <span data-ttu-id="8bc60-137">En la página **Destinos** , administre los servidores de destino del trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bc60-137">On the **Targets** page, manage the target servers for the job.</span></span> <span data-ttu-id="8bc60-138">Para obtener más información sobre las opciones disponibles en esta página, vea [propiedades del trabajo: nuevo trabajo &#40;página destinos&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="8bc60-138">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
10. <span data-ttu-id="8bc60-139">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8bc60-139">When finished, click **OK**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8bc60-140">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8bc60-140">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-master-sql-server-agent-job"></a><span data-ttu-id="8bc60-141">Para crear un trabajo principal del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="8bc60-141">To create a master SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="8bc60-142">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bc60-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8bc60-143">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="8bc60-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8bc60-144">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="8bc60-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- Adds a new job executed by the SQLServerAgent service called 'Weekly Sales Data Backup'  
    EXEC dbo.sp_add_job  
        @job_name = N'Weekly Sales Data Backup' ;  
    GO  
    -- Adds a step (operation) to the 'Weekly Sales Data Backup' job.  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    -- Creates a schedule called RunOnce  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
    USE msdb ;  
    GO  
    -- Sets the 'RunOnce' schedule to the "Weekly Sales Data Backup' Job  
    EXEC sp_attach_schedule  
       @job_name = N'Weekly Sales Data Backup',  
       @schedule_name = N'RunOnce';  
    GO  
    -- assigns the multiserver job Weekly Sales Backups to the server SEATTLE2  
    -- assumes that SEATTLE2 is registered as a target server for the current instance.  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Data Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="8bc60-145">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="8bc60-145">For more information, see:</span></span>  
  
-   [<span data-ttu-id="8bc60-146">sp_add_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8bc60-146">sp_add_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
  
-   [<span data-ttu-id="8bc60-147">sp_add_jobstep &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8bc60-147">sp_add_jobstep &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="8bc60-148">sp_add_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8bc60-148">sp_add_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)  
  
-   [<span data-ttu-id="8bc60-149">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8bc60-149">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="8bc60-150">sp_add_jobserver &#40;&#41;de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8bc60-150">sp_add_jobserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  

  
  
