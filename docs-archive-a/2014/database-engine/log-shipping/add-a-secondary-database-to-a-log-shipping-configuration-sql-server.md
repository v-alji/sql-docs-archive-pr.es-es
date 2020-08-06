---
title: Agregar una base de datos secundaria a la configuración del trasvase de registros (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- adding secondary databases
- secondary databases [SQL Server], in log shipping
- secondary data files [SQL Server], adding
- log shipping [SQL Server], secondary databases
ms.assetid: b02eba13-f8e6-4684-b7e4-75ea038ea473
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 062df1b53ed74321ba0c75c9df763de79a4802bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673243"
---
# <a name="add-a-secondary-database-to-a-log-shipping-configuration-sql-server"></a><span data-ttu-id="fe6f6-102">Agregar una base de datos secundaria a la configuración del trasvase de registros (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fe6f6-102">Add a Secondary Database to a Log Shipping Configuration (SQL Server)</span></span>
  <span data-ttu-id="fe6f6-103">En este tema se describe cómo agregar una base de datos secundaria a una configuración de trasvase de registros de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] existente mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe6f6-103">This topic describes how to add a secondary database to an existing log shipping configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="fe6f6-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="fe6f6-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fe6f6-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="fe6f6-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fe6f6-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fe6f6-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fe6f6-107">**Para agregar una base de datos secundaria de trasvase de registros con:**</span><span class="sxs-lookup"><span data-stu-id="fe6f6-107">**To add a log shipping secondary database, using:**</span></span>  
  
     [<span data-ttu-id="fe6f6-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fe6f6-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fe6f6-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fe6f6-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="fe6f6-110">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="fe6f6-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fe6f6-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="fe6f6-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fe6f6-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fe6f6-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fe6f6-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="fe6f6-113">Permissions</span></span>  
 <span data-ttu-id="fe6f6-114">Los procedimientos almacenados de trasvase de registros requieren que se pertenezca al rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="fe6f6-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fe6f6-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fe6f6-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-a-log-shipping-secondary-database"></a><span data-ttu-id="fe6f6-116">Para agregar una base de datos secundaria de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="fe6f6-116">To add a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="fe6f6-117">Haga clic con el botón derecho en la base de datos que quiera usar como base de datos principal en la configuración de trasvase de registros y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-117">Right-click the database you want to use as your primary database in the log shipping configuration, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="fe6f6-118">En **Seleccionar una página**, haga clic en **Trasvase de registro de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-118">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
3.  <span data-ttu-id="fe6f6-119">En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-119">Under **Secondary server instances and databases**, click **Add**.</span></span>  
  
4.  <span data-ttu-id="fe6f6-120">Haga clic en **Conectar** para conectarse a la sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que desee utilizar como servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-120">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your secondary server.</span></span>  
  
5.  <span data-ttu-id="fe6f6-121">En el cuadro **Base de datos secundaria** , elija una base de datos de la lista o escriba el nombre de la base de datos que desea crear.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-121">In the **Secondary database** box, choose a database from the list or type the name of the database you want to create.</span></span>  
  
6.  <span data-ttu-id="fe6f6-122">En la pestaña **Inicializar base de datos secundaria** , elija la opción que desee utilizar para inicializar la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-122">On the **Initialize Secondary database** tab, choose the option that you want to use to initialize the secondary database.</span></span>  
  
7.  <span data-ttu-id="fe6f6-123">En la pestaña **Copiar archivos**, en el cuadro **Carpeta de destino de los archivos copiados** , escriba la ruta de la carpeta en la que se van a copiar las copias de seguridad de los registros de transacciones.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-123">On the **Copy Files tab**, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="fe6f6-124">Esta carpeta normalmente está situada en el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-124">This folder is often located on the secondary server.</span></span>  
  
8.  <span data-ttu-id="fe6f6-125">Tenga presente la programación de copia que aparece en el cuadro **Programación** bajo **Trabajo de copia**.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="fe6f6-126">Si desea personalizar la programación de su instalación, haga clic en **Programar** y, a continuación, ajuste la programación del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-126">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="fe6f6-127">El programa debe parecerse al de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-127">This schedule should approximate the backup schedule.</span></span>  
  
9. <span data-ttu-id="fe6f6-128">En la pestaña **Restaurar** , en **Estado de la base de datos al restaurar copias de seguridad**, elija la opción **Modo sin recuperación** o **Modo de espera** .</span><span class="sxs-lookup"><span data-stu-id="fe6f6-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** or **Standby mode** option.</span></span>  
  
10. <span data-ttu-id="fe6f6-129">Si elige la opción **Modo de espera** , seleccione si desea desconectar a los usuarios de la base de datos secundaria mientras se realiza la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-129">If you chose the **Standby mode** option, choose if you want to disconnect users from the secondary database while the restore operation is underway.</span></span>  
  
11. <span data-ttu-id="fe6f6-130">Si desea retrasar el proceso de restauración en el servidor secundario, elija un tiempo de retraso en **Retrasar la restauración de las copias de seguridad al menos**.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-130">If you want to delay the restore process on the secondary server, choose a delay time under **Delay restoring backups at least**.</span></span>  
  
12. <span data-ttu-id="fe6f6-131">Elija un umbral de alerta en **Mostrar una alerta si no se produce una restauración tras**.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-131">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>  
  
13. <span data-ttu-id="fe6f6-132">Tenga presente la programación de la restauración que aparece en el cuadro **Programación** bajo **Trabajo de restauración**.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-132">Note the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="fe6f6-133">Si desea personalizar la programación de su instalación, haga clic en **Programar** y, a continuación, ajuste la programación del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-133">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="fe6f6-134">El programa debe parecerse al de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-134">This schedule should approximate the backup schedule.</span></span>  
  
14. <span data-ttu-id="fe6f6-135">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-135">Click **OK**.</span></span>  
  
15. <span data-ttu-id="fe6f6-136">Haga clic en **Aceptar** en el cuadro de diálogo Propiedades de la base de datos para empezar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-136">Click **OK** on the Database Properties dialog box to begin the configuration process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fe6f6-137">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fe6f6-137">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-log-shipping-secondary-database"></a><span data-ttu-id="fe6f6-138">Para agregar una base de datos secundaria de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="fe6f6-138">To add a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="fe6f6-139">En el servidor secundario, ejecute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) y proporcione los detalles del servidor y la base de datos principales.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-139">On the secondary server, execute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) supplying the details of the primary server and database.</span></span> <span data-ttu-id="fe6f6-140">Este procedimiento almacenado devuelve el Id. secundario y los Id. de los trabajos de copia y restauración.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-140">This stored procedure returns the secondary ID and the copy and restore job IDs.</span></span>  
  
2.  <span data-ttu-id="fe6f6-141">En el servidor secundario, ejecute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) para establecer la programación de los trabajos de copia y restauración.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-141">On the secondary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to set the schedule for the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="fe6f6-142">En el servidor secundario, ejecute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) para agregar una base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-142">On the secondary server, execute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) to add a secondary database.</span></span>  
  
4.  <span data-ttu-id="fe6f6-143">En el servidor principal, ejecute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) para agregar la información necesaria sobre la nueva base de datos secundaria al servidor principal.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-143">On the primary server, execute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) to add the required information about the new secondary database to the primary server.</span></span>  
  
5.  <span data-ttu-id="fe6f6-144">En el servidor secundario, habilite los trabajos de copia y restauración.</span><span class="sxs-lookup"><span data-stu-id="fe6f6-144">On the secondary server, enable the copy and restore jobs.</span></span> <span data-ttu-id="fe6f6-145">Para obtener más información, consulte [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="fe6f6-145">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="fe6f6-146">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="fe6f6-146">Related Tasks</span></span>  
  
-   [<span data-ttu-id="fe6f6-147">Actualizar el trasvase de registros a SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fe6f6-147">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="fe6f6-148">Configurar el trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe6f6-148">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="fe6f6-149">Quitar una base de datos secundaria desde una configuración de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe6f6-149">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="fe6f6-150">Quitar el trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe6f6-150">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="fe6f6-151">Ver el informe de trasvase de registros &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="fe6f6-151">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="fe6f6-152">Supervisar el trasvase de registros &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fe6f6-152">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="fe6f6-153">Conmutar por error a una base de datos secundaria de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe6f6-153">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="fe6f6-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fe6f6-154">See Also</span></span>  
 <span data-ttu-id="fe6f6-155">[Acerca del trasvase de registros &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fe6f6-155">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="fe6f6-156">Tablas y procedimientos almacenados de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="fe6f6-156">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
