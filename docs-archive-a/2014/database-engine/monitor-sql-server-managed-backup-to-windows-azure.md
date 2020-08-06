---
title: Supervisión de SQL Server copia de seguridad administrada en Azure | Microsoft Docs
description: En este artículo se describen las herramientas que puede usar para determinar el estado general de las copias de seguridad con SQL Server copia de seguridad administrada en Azure e identificar los errores.
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: cfb9e431-7d4c-457c-b090-6f2528b2f315
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: baec99e63c70befde0cfce76e42dd6202ebc0bad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676664"
---
# <a name="monitor-sql-server-managed-backup-to-azure"></a><span data-ttu-id="15f1c-103">Supervisión de copia de seguridad administrada de SQL Server en Azure</span><span class="sxs-lookup"><span data-stu-id="15f1c-103">Monitor SQL Server Managed Backup to Azure</span></span>
  [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="15f1c-104">tiene medidas integradas para identificar los problemas y los errores durante los procesos de copia de seguridad y remediarlos con la acción correctiva, si es posible.</span><span class="sxs-lookup"><span data-stu-id="15f1c-104">has built-in measures to identify problems and errors during backup processes and remedy with corrective action when possible.</span></span>  <span data-ttu-id="15f1c-105">Aunque hay ciertas situaciones en las que se requiere la intervención del usuario.</span><span class="sxs-lookup"><span data-stu-id="15f1c-105">However there are certain situations where user intervention is required.</span></span> <span data-ttu-id="15f1c-106">Este tema describe las herramientas que puede utilizar para determinar el estado de mantenimiento total de las copias de seguridad e identificar los errores que deban solucionarse.</span><span class="sxs-lookup"><span data-stu-id="15f1c-106">This topic describes the tools that you can use to determine the overall health status of backups, and identify any errors that need to be addressed.</span></span>  
  
## <a name="overview-of-ss_smartbackup-built-in-debugging"></a><span data-ttu-id="15f1c-107">Introducción a la depuración integrada de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15f1c-107">Overview of [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Built-in Debugging</span></span>  
 <span data-ttu-id="15f1c-108">El [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] revisa periódicamente las copias de seguridad programadas e intenta volver a programar las que no se hayan podido realizar.</span><span class="sxs-lookup"><span data-stu-id="15f1c-108">The [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] periodically reviews scheduled backups and attempts to reschedule any failed backups.</span></span> <span data-ttu-id="15f1c-109">Sondea periódicamente la cuenta de almacenamiento para identificar las interrupciones en las cadenas de registros que afectan a la capacidad de recuperación de la base de datos y programa las nuevas copias de seguridad en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="15f1c-109">It polls the storage account periodically to identify breaks in log chains affecting recoverability of the database, and schedules new backups accordingly.</span></span> <span data-ttu-id="15f1c-110">También tiene en cuenta las directivas de limitación de Azure y tiene mecanismos para administrar varias copias de seguridad de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="15f1c-110">It also takes into account Azure throttling policies, and has mechanisms in place to manage multiple database backups.</span></span> [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="15f1c-111">usa eventos extendidos para realizar el seguimiento de todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="15f1c-111">uses extended events to track all activity.</span></span> <span data-ttu-id="15f1c-112">Los canales de eventos extendidos que usa el agente [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] son el de administración, operativo, analítico y depuración.</span><span class="sxs-lookup"><span data-stu-id="15f1c-112">The Extended Event channels used by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] agent include, Admin, Operational, Analytical, and Debug.</span></span> <span data-ttu-id="15f1c-113">Los eventos que entran en la categoría de administración suelen relacionarse con errores y requerir la intervención del usuario y se habilitan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="15f1c-113">Events that fall under the Admin category usually are related to errors and require user intervention and are enabled by default.</span></span> <span data-ttu-id="15f1c-114">Los eventos analíticos se activan de forma predeterminada pero por lo general no están relacionados con errores que requieran la intervención del usuario.</span><span class="sxs-lookup"><span data-stu-id="15f1c-114">Analytical events are also turned on by default, but usually are not related to errors that require user intervention.</span></span> <span data-ttu-id="15f1c-115">Los eventos operativos suelen ser informativos.</span><span class="sxs-lookup"><span data-stu-id="15f1c-115">Operation events are typically informational.</span></span> <span data-ttu-id="15f1c-116">Por ejemplo, los eventos operativos incluyen la programación de una copia de seguridad, la finalización correcta de una copia de seguridad, etc. La depuración es la más detallada y se usa internamente [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para determinar los problemas y corregirlos si es necesario.</span><span class="sxs-lookup"><span data-stu-id="15f1c-116">For example, operational events include scheduling a backup, a successful completion of backup, etc. The Debug is the most verbose and is used internally by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] to determine issues and correct them if required.</span></span>  
  
### <a name="configure-monitoring-parameters-for-ss_smartbackup"></a><span data-ttu-id="15f1c-117">Configurar parámetros de supervisión para [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15f1c-117">Configure Monitoring Parameters for [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]</span></span>  
 <span data-ttu-id="15f1c-118">El procedimiento almacenado del sistema **smart_admin. sp_set_parameter** le permite especificar la configuración de supervisión.</span><span class="sxs-lookup"><span data-stu-id="15f1c-118">The **smart_admin.sp_set_parameter** system stored procedure allows you to specify monitoring settings.</span></span> <span data-ttu-id="15f1c-119">En las secciones siguientes se recorre el proceso para habilitar Eventos extendidos y para habilitar la notificación por correo electrónico de los errores y las advertencias.</span><span class="sxs-lookup"><span data-stu-id="15f1c-119">The following sections walks through the process of enabling Extended Events,  and enabling email notification for errors and warnings.</span></span>  
  
 <span data-ttu-id="15f1c-120">La función **smart_admin. fn_get_parameter** se puede utilizar para obtener la configuración actual de un parámetro concreto o de todos los parámetros configurados.</span><span class="sxs-lookup"><span data-stu-id="15f1c-120">The **smart_admin.fn_get_parameter** function can be used to get the current setting for a specific parameter or all configured parameters.</span></span> <span data-ttu-id="15f1c-121">Si los parámetros no se han configurado nunca, la función no devuelve ningún valor.</span><span class="sxs-lookup"><span data-stu-id="15f1c-121">If the parameters have never been configured, the function does not return any values.</span></span>  
  
1.  <span data-ttu-id="15f1c-122">Conéctese con el [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15f1c-122">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="15f1c-123">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="15f1c-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="15f1c-124">Copie y pegue el ejemplo siguiente en la ventana de consulta y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="15f1c-124">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="15f1c-125">De este modo se devuelve la configuración actual de Eventos extendidos y las notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="15f1c-125">This will return the current configuration for Extended Events, and e-mail notifications.</span></span>  
  
```sql
Use msdb  
Go  
SELECT * FROM smart_admin.fn_get_parameter (NULL)  
GO  
```  
  
 <span data-ttu-id="15f1c-126">Para obtener más información, vea [smart_admin. fn_get_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-parameter-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="15f1c-126">For more information, see [smart_admin.fn_get_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-parameter-transact-sql)</span></span>  
  
### <a name="extended-events-for-monitoring"></a><span data-ttu-id="15f1c-127">Eventos extendidos para la supervisión</span><span class="sxs-lookup"><span data-stu-id="15f1c-127">Extended Events for Monitoring</span></span>  
 <span data-ttu-id="15f1c-128">De forma predeterminada, los eventos de administración, operativos y analíticos están activados.</span><span class="sxs-lookup"><span data-stu-id="15f1c-128">By default, Admin, Operational and Analytical events are turned on.</span></span> <span data-ttu-id="15f1c-129">Los eventos de administración son los más importantes, útiles para identificar los errores que requieren intervención manual para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="15f1c-129">Admin events are most critical, useful when identifying errors that require manual intervention to solve the problem.</span></span> <span data-ttu-id="15f1c-130">Puede ser conveniente activar los eventos operativos y de depuración pero debe tener en cuenta que son muy detallados y pueden requerir un filtrado.</span><span class="sxs-lookup"><span data-stu-id="15f1c-130">You may want to turn on the operational and debug events but consider that these events are verbose and may require some filtering.</span></span> <span data-ttu-id="15f1c-131">Los procedimientos siguientes describen cómo supervisar los eventos registrados mediante Eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="15f1c-131">The following procedures describe how to monitor events logged through Extended Events.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="15f1c-132">A diferencia de Eventos extendidos para el Motor SQL, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] no admite los conceptos relativos a la sesión de Eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="15f1c-132">Unlike Extended Events for SQL Engine, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] does not support Extended Event session concepts.</span></span> <span data-ttu-id="15f1c-133">Las funciones y los procedimientos almacenados del sistema son las herramientas que se usan para interactuar con los eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="15f1c-133">System stored procedures and functions are the tools used to interact with extended events.</span></span> <span data-ttu-id="15f1c-134">También puede ver el registro de eventos extendidos desde el directorio de registro.</span><span class="sxs-lookup"><span data-stu-id="15f1c-134">You can also view the extended event log from the log directory.</span></span>  
  
##### <a name="to-configure-and-view-extended-events"></a><span data-ttu-id="15f1c-135">Para configurar y ver Eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="15f1c-135">To Configure and View Extended Events</span></span>  
  
1.  <span data-ttu-id="15f1c-136">Para ver los canales de Eventos extendidos disponibles y su estado actual ejecutando la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="15f1c-136">To view available Extended Event channels and their current status by running the following query:</span></span>  
  
    ```sql
    SELECT * FROM smart_admin.fn_get_current_xevent_settings()  
    ```  
  
     <span data-ttu-id="15f1c-137">El resultado de esta consulta mostrará el event_name, si es configurable o no, y si está habilitado.</span><span class="sxs-lookup"><span data-stu-id="15f1c-137">The output from this query will display the event_name, whether it is configurable or not, and whether it is currently enabled.</span></span>  <span data-ttu-id="15f1c-138">Para obtener más información, vea [smart_admin. fn_get_current_xevent_settings &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-functions/managed-backup-fn-get-current-xevent-settings-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15f1c-138">For more information, see [smart_admin.fn_get_current_xevent_settings &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-get-current-xevent-settings-transact-sql).</span></span>  
  
2.  <span data-ttu-id="15f1c-139">Para habilitar los eventos de depuración, ejecute la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="15f1c-139">To enable debug events, run the following query:</span></span>  
  
    ```sql
    --  to enable debug events  
    Use msdb;  
    GO 
    EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
    ```  
  
     <span data-ttu-id="15f1c-140">Para obtener más información acerca del procedimiento almacenado, vea [smart_admin. sp_set_parameter &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/managed-backup-sp-set-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15f1c-140">For more information about the stored procedure, see [smart_admin.sp_set_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/managed-backup-sp-set-parameter-transact-sql).</span></span>  
  
3.  <span data-ttu-id="15f1c-141">Para ver los eventos registrados, ejecute la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="15f1c-141">To view the logged events run the following query:</span></span>  
  
    ```sql
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;
    ```  
  
    ```sql
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event nvarchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'
    ```  
  
### <a name="aggregated-error-countshealth-status"></a><span data-ttu-id="15f1c-142">Estado de mantenimiento y recuentos de errores agregados</span><span class="sxs-lookup"><span data-stu-id="15f1c-142">Aggregated Error Counts/Health Status</span></span>  
 <span data-ttu-id="15f1c-143">La función **smart_admin. fn_get_health_status** devuelve una tabla de recuentos de errores agregados para cada categoría que se puede usar para supervisar el estado de mantenimiento de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15f1c-143">The **smart_admin.fn_get_health_status** function returns a table of aggregated error counts for each category that can be used to monitor the health status of [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="15f1c-144">Esta misma función también la utiliza el mecanismo de notificación por correo electrónico configurado en el sistema que se describe más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="15f1c-144">This same function is also used by the system configured e-mail notification mechanism described later in this topic.</span></span>   
<span data-ttu-id="15f1c-145">Estos recuentos agregados se pueden utilizar para supervisar el estado del sistema.</span><span class="sxs-lookup"><span data-stu-id="15f1c-145">These aggregated counts can be used to monitor system health.</span></span> <span data-ttu-id="15f1c-146">Por ejemplo, si el number_ of_retention_loops columna es 0 en 30 minutos, es posible que la administración de la retención tarde mucho tiempo o incluso no funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="15f1c-146">For example, if the number_ of_retention_loops column is 0 in 30 minutes, it is possible that retention management is taking long time or even not working correctly.</span></span> <span data-ttu-id="15f1c-147">Las columnas de errores que no son cero pueden indicar que hay problemas y los registros de Eventos extendidos se deben comprobar para detectarlos.</span><span class="sxs-lookup"><span data-stu-id="15f1c-147">Non-zero error columns may indicate problems and Extended Events logs should be checked to discover the problem.</span></span> <span data-ttu-id="15f1c-148">También puede llamar a **smart_admin. sp_get_backup_diagnostics** procedimiento almacenado para buscar los detalles del error.</span><span class="sxs-lookup"><span data-stu-id="15f1c-148">Alternatively, call **smart_admin.sp_get_backup_diagnostics** stored procedure to find the details of the error.</span></span>  
  
### <a name="using-agent-notification-for-assessing-backup-status-and-health"></a><span data-ttu-id="15f1c-149">Usar la notificación del agente para evaluar el estado de la copia de seguridad y los estados</span><span class="sxs-lookup"><span data-stu-id="15f1c-149">Using Agent Notification for Assessing Backup Status and Health</span></span>  
 [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="15f1c-150">incluye un mecanismo de notificación que se fundamenta en las directivas de administración basada en directivas de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="15f1c-150">includes a notification mechanism that is based on SQL Server policy based management policies.</span></span>  
  
 <span data-ttu-id="15f1c-151">**Requisitos previos:**</span><span class="sxs-lookup"><span data-stu-id="15f1c-151">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="15f1c-152">Para usar esta funcionalidad, se requiere el Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="15f1c-152">Database Mail is required to use this functionality.</span></span> <span data-ttu-id="15f1c-153">Para obtener más información acerca de cómo habilitar el correo electrónico de base de datos para la instancia de SQL Server, vea [configurar correo electrónico de base de datos](../relational-databases/database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="15f1c-153">For more information, about how to enable DB Mail for the instance of SQL Server, see [Configure Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span></span>  
  
-   <span data-ttu-id="15f1c-154">Las propiedades del sistema de alertas del Agente SQL Server se deben establecer para utilizar el Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="15f1c-154">SQL Server Agent Alert System properties should be set to use Database Mail.</span></span>  
  
 <span data-ttu-id="15f1c-155">**Arquitectura de notificación:**</span><span class="sxs-lookup"><span data-stu-id="15f1c-155">**Notification Architecture:**</span></span>  
  
-   <span data-ttu-id="15f1c-156">**Administración basada en directivas:** Se establecen dos directivas para supervisar el estado de la copia de seguridad: **Directiva de mantenimiento del sistema de administración inteligente**y la **Directiva de estado de acción de usuario de administrador inteligente**.</span><span class="sxs-lookup"><span data-stu-id="15f1c-156">**Policy Based Management:** Two policies are set to monitor backup health: **Smart Admin System Health Policy**, and the **Smart Admin User Action Health Policy**.</span></span> <span data-ttu-id="15f1c-157">La directiva de estado del sistema de Administración inteligente evalúa los errores críticos como la falta de credenciales de SQL o si no son válidas y los errores de conectividad y notifica el estado del sistema.</span><span class="sxs-lookup"><span data-stu-id="15f1c-157">The Smart Admin System Health Policy evaluates critical errors like lack of or invalid SQL Credentials, connectivity errors and reports the health of the system.</span></span> <span data-ttu-id="15f1c-158">Se suele requerir intervención para solucionar el problema subyacente.</span><span class="sxs-lookup"><span data-stu-id="15f1c-158">These typically require a manual action to correct the underlying issue.</span></span> <span data-ttu-id="15f1c-159">La directiva de estado de acción del usuario de Administración inteligente evalúa las advertencias, por ejemplo las copias de seguridad dañadas.</span><span class="sxs-lookup"><span data-stu-id="15f1c-159">The Smart Admin User Action Health Policy evaluates warnings such as corrupted backups, and such.</span></span>  <span data-ttu-id="15f1c-160">Estas pueden no requerir ninguna intervención sino que solo son una advertencia de un evento.</span><span class="sxs-lookup"><span data-stu-id="15f1c-160">These may not require any action but just a warning of an event.</span></span> <span data-ttu-id="15f1c-161">Se espera que el agente [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] se ocupe de tales problemas.</span><span class="sxs-lookup"><span data-stu-id="15f1c-161">It is expected that such issues will be automatically taken care of by [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] agent.</span></span>  
  
-   <span data-ttu-id="15f1c-162">**Agente SQL Server** Trabajo: la notificación se realiza mediante un trabajo Agente SQL Server que tiene tres pasos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="15f1c-162">**SQL Server Agent** Job: The notification is performed using a SQL Server Agent job that has three job steps.</span></span> <span data-ttu-id="15f1c-163">En el primer paso, detecta si [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] está configurado para una base de datos o una instancia.</span><span class="sxs-lookup"><span data-stu-id="15f1c-163">In the first job step it detects to see whether [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is configured for a database or instance.</span></span> <span data-ttu-id="15f1c-164">Si encuentra [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] habilitado y configurado, realiza el segundo paso: ejecuta el cmdlet de PowerShell que evalúa el estado evaluando las directivas de administración basada en directivas de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="15f1c-164">If it finds [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled and configured, it executes the second step: executes a PowerShell cmdlet that assess the health status by evaluating the SQL Server policy based management policies.</span></span> <span data-ttu-id="15f1c-165">Si detecta un error o una advertencia, da error y desencadena el tercer paso: envía una notificación por correo electrónico con el informe de la advertencia o el error.</span><span class="sxs-lookup"><span data-stu-id="15f1c-165">If it finds either an error or warning, it fails which then triggers the third step: The third step sends out an e-mail notification with the error/warning report.</span></span>  <span data-ttu-id="15f1c-166">Sin embargo, este trabajo del Agente SQL Server no está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="15f1c-166">However this SQL Server Agent job is not enabled by default.</span></span> <span data-ttu-id="15f1c-167">Para habilitar el trabajo de notificación de correo electrónico, utilice el procedimiento almacenado del sistema **smart_admin. sp_set_backup_parameter** .</span><span class="sxs-lookup"><span data-stu-id="15f1c-167">To enable the e-mail notification job, use the **smart_admin.sp_set_backup_parameter** system stored procedure.</span></span>  <span data-ttu-id="15f1c-168">En el siguiente procedimiento se describen los pasos detalladamente:</span><span class="sxs-lookup"><span data-stu-id="15f1c-168">The following procedure describes the steps in more detail:</span></span>  
  
##### <a name="enabling-email-notification"></a><span data-ttu-id="15f1c-169">Habilitar la notificación por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="15f1c-169">Enabling Email Notification</span></span>  
  
1.  <span data-ttu-id="15f1c-170">Si aún no se ha configurado Correo electrónico de base de datos, siga los pasos descritos en [configurar correo electrónico de base de datos](../relational-databases/database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="15f1c-170">If Database Mail is not already configured, use the steps described in [Configure Database Mail](../relational-databases/database-mail/configure-database-mail.md).</span></span>  
  
2.  <span data-ttu-id="15f1c-171">Establecer la base de datos como sistema de correo para SQL Server sistema de alerta: haga clic con el botón secundario en **Agente SQL Server**, seleccione **sistema de alerta**, active la casilla **Habilitar perfil de correo** , seleccione **correo electrónico de base de datos** como **sistema de correo**y seleccione un perfil de correo creado previamente.</span><span class="sxs-lookup"><span data-stu-id="15f1c-171">Set database as the Mail System for SQL Server Alert System: Right Click on **SQL Server Agent**, select **Alert System**, check the **Enable mail profile** box, Select **Database Mail** as the **Mail System**, and select a previously created Mail profile.</span></span>  
  
3.  <span data-ttu-id="15f1c-172">Ejecute la consulta siguiente en una ventana de consulta y proporcione la dirección de correo electrónico a la que desea que se envíe la notificación:</span><span class="sxs-lookup"><span data-stu-id="15f1c-172">Run the following query in a query window and provide the e-mail address where you want the notification to be sent to:</span></span>  
  
    ```sql
    Use msdb  
    Go  
    EXEC smart_admin.sp_set_parameter @parameter_name = 'SSMBackup2WANotificationEmailIds', @parameter_value = '<email address>'
    ```  
  
     <span data-ttu-id="15f1c-173">Así se crea un trabajo del Agente SQL Server que se utiliza para recopilar el estado y enviar notificaciones cuando se produce un error o un problema con las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="15f1c-173">This creates a SQL Server Agent job that is used to gather health status and send notifications when there is an error or an issue with backups.</span></span>  
  
 <span data-ttu-id="15f1c-174">A continuación se muestra un script de ejemplo para habilitar Correo electrónico de base de datos y configurar la notificación por correo electrónico mediante el trabajo del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="15f1c-174">Following is a sample script  to enable DB Mail and set up the e-mail notification through SQL Server Agent Job</span></span>  
  
```sql
-- Prereq: Make sure that SQL Server service runs in a service account that has  
--  access to SMTP Server   
-- set SQL Server service account as domain account   
  
EXEC sp_configure 'show advanced', 1  
RECONFIGURE  
GO  
  
-- Enable DBMail  
EXEC sp_configure 'Database Mail XPs',1  
GO  
RECONFIGURE  
GO  
  
-- Configure DBMail  
DECLARE @emailid NVARCHAR(255)  
-- Note: change this email to your own email id  
SET @emailid = N'emailalias@mycompany.com'  
  
DECLARE @smtpserver NVARCHAR(255)  
SET @smtpserver = N'smtphost.domainname.com'  
  
DECLARE @mailprofile NVARCHAR(255)  
SET @mailprofile = N'my_profile'  
  
EXEC msdb.dbo.sysmail_add_account_sp @account_name=N'myaccount',  
                @email_address = @emailid,  
                @replyto_address = @emailid,  
                @mailserver_name = @smtpserver,  
                @use_default_credentials = 1  
  
EXEC msdb.dbo.sysmail_add_profile_sp @profile_name=@mailprofile  
EXEC msdb.dbo.sysmail_add_profileaccount_sp @profile_name=@mailprofile, @account_name=N'myaccount', @sequence_number=1  
  
-- Set SQL Agent to use DBMail profile  
EXEC msdb.dbo.sp_set_sqlagent_properties @databasemail_profile = @mailprofile  
  
-- Configure Notifications   
EXEC msdb.smart_admin.sp_set_parameter  
@parameter_name = 'SSMBackup2WANotificationEmailIds',  
@parameter_value = @emailid  
  
-- To test is you are receiving notifications  
-- delete few backup files from your storage container, Wait for 15 minutes & see if you get any email notification
```  
  
### <a name="using-powershell-to-setup-custom-health-monitoring"></a><span data-ttu-id="15f1c-175">Usar PowerShell para configurar la supervisión personalizada del estado</span><span class="sxs-lookup"><span data-stu-id="15f1c-175">Using PowerShell to Setup Custom Health Monitoring</span></span>  
 <span data-ttu-id="15f1c-176">El cmdlet **Test-SqlSmartAdmin** se puede usar para crear una supervisión de estado personalizada.</span><span class="sxs-lookup"><span data-stu-id="15f1c-176">The **Test-SqlSmartAdmin** cmdlet can be used to create custom health monitoring.</span></span> <span data-ttu-id="15f1c-177">Por ejemplo, la opción de notificación descrita en la sección anterior se puede configurar en el nivel de instancia.</span><span class="sxs-lookup"><span data-stu-id="15f1c-177">For example, the notification option described in the previous section can be configured at the instance level.</span></span>  <span data-ttu-id="15f1c-178">Si tiene varias instancias de SQL Server configuradas para utilizar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], el cmdlet de PowerShell se puede utilizar para crear scripts y recopilar el estado de las copias de seguridad de todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="15f1c-178">If you have several instances of SQL Server configured to use [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], the PowerShell cmdlet can be used to create scripts in gather the status and health of backups for all the instances.</span></span>  
  
 <span data-ttu-id="15f1c-179">El cmdlet **Test-SqlSmartAdmin** evalúa los errores y las advertencias que devuelve el SQL Server directivas de administración basadas en directivas y notifica el estado acumulado.</span><span class="sxs-lookup"><span data-stu-id="15f1c-179">The **Test-SqlSmartAdmin** cmdlet assesses the errors and warnings returned by the SQL Server Policy Based Management policies and reports out a rolled up status.</span></span>  <span data-ttu-id="15f1c-180">De forma predeterminada, este cmdlet utiliza las directivas del sistema.</span><span class="sxs-lookup"><span data-stu-id="15f1c-180">By default this cmdlet uses the system policies.</span></span> <span data-ttu-id="15f1c-181">Para incluir una directiva personalizada, utilice el parámetro `-AllowUserPolicies`.</span><span class="sxs-lookup"><span data-stu-id="15f1c-181">To include any custom policy use the `-AllowUserPolicies` parameter.</span></span>  
  
 <span data-ttu-id="15f1c-182">A continuación se muestra un script de PowerShell de ejemplo que devuelve un informe de los errores y las advertencias basados en las directivas de sistema y de las directivas de usuario creadas:</span><span class="sxs-lookup"><span data-stu-id="15f1c-182">Following is a sample PowerShell script that returns a report of errors and warnings based on the system policies and any user policies created:</span></span>  
  
```powershell
$policyResults = Get-SqlSmartAdmin | Test-SqlSmartAdmin -AllowUserPolicies  
$policyResults.PolicyEvaluationDetails | Select Name, Category, Expression, Result, Exception | fl
```  
  
 <span data-ttu-id="15f1c-183">El script siguiente devuelve un informe detallado de los errores y advertencias de la instancia predeterminada ( `\SQL\COMPUTER\DEFAULT` ):</span><span class="sxs-lookup"><span data-stu-id="15f1c-183">The following script returns a detailed report of the errors and warnings for the default instance (`\SQL\COMPUTER\DEFAULT`):</span></span>  
  
```powershell
(Get-SqlSmartAdmin ).EnumHealthStatus()  
```  
  
### <a name="objects-in-msdb-database"></a><span data-ttu-id="15f1c-184">Objetos de la base de datos MSDB</span><span class="sxs-lookup"><span data-stu-id="15f1c-184">Objects in MSDB database</span></span>  
 <span data-ttu-id="15f1c-185">Hay objetos que se instalan para implementar la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="15f1c-185">There are objects that are installed to implement the functionality.</span></span> <span data-ttu-id="15f1c-186">Estos objetos están reservados para uso interno.</span><span class="sxs-lookup"><span data-stu-id="15f1c-186">These objects are reserved for internal use.</span></span> <span data-ttu-id="15f1c-187">Sin embargo, hay una tabla del sistema que puede ser útil a la hora supervisar el estado de la copia de seguridad: smart_backup_files.</span><span class="sxs-lookup"><span data-stu-id="15f1c-187">However, there is one system table that can be useful in monitoring the backup status: smart_backup_files.</span></span> <span data-ttu-id="15f1c-188">La mayor parte de la información almacenada en esta tabla relevante para la supervisión como el tipo de copia de seguridad, el nombre de la base de datos, el primer y último LSN, las fechas de expiración de copia de seguridad se exponen a través de la función del sistema [smart_admin&#41;&#40;fn_available_backups. ](/sql/relational-databases/system-functions/managed-backup-fn-available-backups-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="15f1c-188">Most of the Information   stored in this table relevant to monitoring like the type of backup, database name, first and last lsn, backup expiry dates are exposed through the system function [smart_admin.fn_available_backups &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/managed-backup-fn-available-backups-transact-sql).</span></span> <span data-ttu-id="15f1c-189">No obstante, la columna state de la tabla smart_backup_files que indica el estado del archivo de copia de seguridad no está disponible con esa función.</span><span class="sxs-lookup"><span data-stu-id="15f1c-189">However the status column in the smart_backup_files table which indicates the status of the backup file is not available using the function.</span></span> <span data-ttu-id="15f1c-190">A continuación se muestra una consulta de ejemplo que puede utilizar para recuperar cierta información, incluido el estado de la tabla del sistema:</span><span class="sxs-lookup"><span data-stu-id="15f1c-190">Following is a sample query you can use to retrieve the some information including the status from the system table:</span></span>  
  
```sql
USE msdb  
GO  
SELECT  
 database_name AS [Database Name] ,backup_path AS [Backup Destination and File]  
,[Backup Type] =  
CASE backup_type  
WHEN 1 THEN 'FULL'  
WHEN 2 THEN 'LOG'  
END  
,[Backup Status] =  
CASE [status]  
WHEN 'A' THEN 'Available'  
WHEN 'B' THEN 'Copy In Progress'  
WHEN 'C' THEN 'Corrupted'  
WHEN 'D' THEN 'Deleted'  
WHEN 'F' THEN 'Copy Failed'  
WHEN 'U' THEN 'Unknown'  
END  
,first_lsn AS [First LSN]  
,last_lsn AS [Last LSN]  
,backup_start_date AS [Backup Start Time]  
,backup_finish_date AS [Backup Completion Time]  
,expiration_date AS [Backup Expiry Date/Time]  
FROM  
smart_backup_files;
```  
  
 <span data-ttu-id="15f1c-191">A continuación se muestra una explicación detallada de los distintos estados devueltos:</span><span class="sxs-lookup"><span data-stu-id="15f1c-191">Following is a detailed explanation of the different status returned:</span></span>  
  
-   <span data-ttu-id="15f1c-192">**Disponible** : Se trata de un archivo de copia de seguridad normal.</span><span class="sxs-lookup"><span data-stu-id="15f1c-192">**Available - A:** This is a normal backup file.</span></span> <span data-ttu-id="15f1c-193">La copia de seguridad se ha completado y también se ha comprobado que está disponible en Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="15f1c-193">The backup has been completed, and also verified that it is available in the Azure storage.</span></span>  
  
-   <span data-ttu-id="15f1c-194">**Copia en curso-B:** Este estado es específico para las bases de datos del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="15f1c-194">**Copy in Progress -B:** This status is specifically for Availability Group databases.</span></span> <span data-ttu-id="15f1c-195">Si [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] detecta una interrupción en la cadena de registro de copia de seguridad, primero intentará identificar la copia de seguridad que pueda haber producido la interrupción en la cadena de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="15f1c-195">If [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] detects a break in the backup log chain, it will first attempt identify the  backup that might have caused the break in backup chain.</span></span> <span data-ttu-id="15f1c-196">Al buscar el archivo de copia de seguridad, intenta copiar el archivo en Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="15f1c-196">On finding the backup file it attempts to copy the file to Azure storage.</span></span> <span data-ttu-id="15f1c-197">Cuando el proceso de copia está en curso, muestra este estado.</span><span class="sxs-lookup"><span data-stu-id="15f1c-197">When the copying process is in progress it will display this status.</span></span>  
  
-   <span data-ttu-id="15f1c-198">**Error de copia-F:** De forma similar a la copia en curso, se trata de bases de datos de grupos de disponibilidad t específicas.</span><span class="sxs-lookup"><span data-stu-id="15f1c-198">**Copy Failed - F:** Similar to Copy In Progress, this is specific t Availability Group databases.</span></span> <span data-ttu-id="15f1c-199">Si se produce un error en el proceso de copia, se marca el estado como F.</span><span class="sxs-lookup"><span data-stu-id="15f1c-199">If the copy process fails, the status is marked as F.</span></span>  
  
-   <span data-ttu-id="15f1c-200">**Dañado-C:** Si [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] no puede comprobar el archivo de copia de seguridad en el almacenamiento mediante la realización de un comando restore HEADER_ONLY incluso después de varios intentos, marca este archivo como dañado.</span><span class="sxs-lookup"><span data-stu-id="15f1c-200">**Corrupted - C:** If [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is unable to verify the backup file in the storage by performing a RESTORE HEADER_ONLY command even after multiple attempts, it marks this file as corrupted.</span></span> [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="15f1c-201">programará una copia de seguridad para asegurarse de que el archivo dañado no produce una interrupción de la cadena de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="15f1c-201">will schedule a backup to ensure that the corrupted file does not result in a break of the backup chain.</span></span>  
  
-   <span data-ttu-id="15f1c-202">**Eliminado-D:** No se encuentra el archivo correspondiente en Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="15f1c-202">**Deleted - D:** The corresponding file cannot be found in the Azure storage.</span></span> [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="15f1c-203">programará una copia de seguridad si el archivo eliminado produce una interrupción en la cadena de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="15f1c-203">will schedule a backup if the deleted file results in a break in the backup chain.</span></span>  
  
-   <span data-ttu-id="15f1c-204">**Desconocido-U:** Este estado indica que [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] aún no se ha podido comprobar la existencia de archivos y sus propiedades en Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="15f1c-204">**Unknown - U:** This status indicated that [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] has not yet been able to verify file existence and its properties in the Azure storage.</span></span> <span data-ttu-id="15f1c-205">La próxima vez que se ejecute el proceso, que es aproximadamente cada 15 minutos, se actualizará este estado.</span><span class="sxs-lookup"><span data-stu-id="15f1c-205">The next time the process runs, which is approximately every 15 minutes, this status will be updated.</span></span>  
