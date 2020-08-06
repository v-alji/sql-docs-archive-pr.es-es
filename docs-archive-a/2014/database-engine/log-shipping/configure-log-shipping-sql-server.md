---
title: Configurar el trasvase de registros (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], enabling
- log shipping [SQL Server], configuring
ms.assetid: c42aa04a-4945-4417-b4c7-50589d727e9c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 269b0ae2980435e507128cc87606f7eb702c2b7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744831"
---
# <a name="configure-log-shipping-sql-server"></a><span data-ttu-id="03719-102">Configurar el trasvase de registros (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="03719-102">Configure Log Shipping (SQL Server)</span></span>
  <span data-ttu-id="03719-103">En este tema se describe cómo configurar el trasvase de registros en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03719-103">This topic describes how to configure log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="03719-104">y las versiones posteriores admiten la compresión de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="03719-104">and later versions support backup compression.</span></span> <span data-ttu-id="03719-105">Al crear una configuración de trasvase de registros, puede controlar el comportamiento de la compresión de copia de seguridad de las copias de seguridad del registro.</span><span class="sxs-lookup"><span data-stu-id="03719-105">When creating a log shipping configuration, you can control the backup compression behavior of log backups.</span></span> <span data-ttu-id="03719-106">Para obtener más información, vea [Compresión de copia de seguridad &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="03719-106">For more information, see [Backup Compression &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span></span>  
  
 <span data-ttu-id="03719-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="03719-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="03719-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="03719-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="03719-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="03719-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="03719-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="03719-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="03719-111">**Para configurar el trasvase de registros mediante:**</span><span class="sxs-lookup"><span data-stu-id="03719-111">**To configure log shipping, using:**</span></span>  
  
     [<span data-ttu-id="03719-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03719-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="03719-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03719-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="03719-114">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="03719-114">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="03719-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="03719-115">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="03719-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="03719-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="03719-117">En la base de datos principal se debe utilizar el modelo de recuperación optimizado para cargas masivas de registros; el cambio de la base de datos al modelo de recuperación simple provocará que el trasvase de registros deje de funcionar.</span><span class="sxs-lookup"><span data-stu-id="03719-117">The primary database must use the full or bulk-logged recovery model; switching the database to simple recovery will cause log shipping to stop functioning.</span></span>  
  
-   <span data-ttu-id="03719-118">Antes de configurar el trasvase de registros, debe crear un recurso compartido para que las copias de seguridad de los registros de transacciones estén disponibles para el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="03719-118">Before you configure log shipping, you must create a share to make the transaction log backups available to the secondary server.</span></span> <span data-ttu-id="03719-119">Se trata de un recurso compartido del directorio donde se generarán las copias de seguridad de los registros de transacciones.</span><span class="sxs-lookup"><span data-stu-id="03719-119">This is a share of the directory where the transaction log backups will be generated.</span></span> <span data-ttu-id="03719-120">Por ejemplo, si realiza una copia de seguridad de los registros de transacciones en el directorio c:\data\tlogs\\, puede crear el recurso compartido \\\\*servidor_principal*\tlogs de ese directorio.</span><span class="sxs-lookup"><span data-stu-id="03719-120">For example, if you back up your transaction logs to the directory c:\data\tlogs\\, you could create the \\\\*primaryserver*\tlogs share of that directory.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="03719-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="03719-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="03719-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="03719-122">Permissions</span></span>  
 <span data-ttu-id="03719-123">Los procedimientos almacenados de trasvase de registros requieren que se pertenezca al rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="03719-123">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="03719-124">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03719-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-log-shipping"></a><span data-ttu-id="03719-125">Para configurar el trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="03719-125">To configure log shipping</span></span>  
  
1.  <span data-ttu-id="03719-126">Haga clic con el botón secundario en la base de datos que desea usar como base de datos principal en la configuración de trasvase de registros y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="03719-126">Right click the database you want to use as your primary database in the log shipping configuration, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="03719-127">En **Seleccionar una página**, haga clic en **Trasvase de registro de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="03719-127">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
3.  <span data-ttu-id="03719-128">Active la casilla **Habilitar ésta como base de datos principal en una configuración de trasvase de registros** .</span><span class="sxs-lookup"><span data-stu-id="03719-128">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>  
  
4.  <span data-ttu-id="03719-129">En **Copias de seguridad de registros de transacciones**, haga clic en **Configuración de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="03719-129">Under **Transaction log backups**, click **Backup Settings**.</span></span>  
  
5.  <span data-ttu-id="03719-130">En el cuadro **Ruta de red a esta carpeta de copia de seguridad** , escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copias de seguridad de los registros de transacciones.</span><span class="sxs-lookup"><span data-stu-id="03719-130">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>  
  
6.  <span data-ttu-id="03719-131">Si la carpeta de copias de seguridad se encuentra en el servidor principal, escriba la ruta de acceso local a la carpeta de copias de seguridad en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta local a la carpeta**</span><span class="sxs-lookup"><span data-stu-id="03719-131">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="03719-132">(si la carpeta de copias de seguridad no está situada en el servidor principal, puede dejar este cuadro vacío).</span><span class="sxs-lookup"><span data-stu-id="03719-132">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="03719-133">Si la cuenta de servicio de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el servidor principal se ejecuta bajo una cuenta del sistema local, debe crear la carpeta de copias de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="03719-133">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>  
  
7.  <span data-ttu-id="03719-134">Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras** .</span><span class="sxs-lookup"><span data-stu-id="03719-134">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>  
  
8.  <span data-ttu-id="03719-135">Tenga presente la programación de copia de seguridad que aparece en el cuadro **Programación** bajo **Trabajo de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="03719-135">Note the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="03719-136">Si desea personalizar la programación de su instalación, a continuación, haga clic en **Programar** y ajuste la programación del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="03719-136">If you want to customize the schedule for your installation, then click **Schedule** and adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span>  
  
9. [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="03719-137">admite la [compresión de copia de seguridad](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="03719-137">supports [backup compression](../../relational-databases/backup-restore/backup-compression-sql-server.md).</span></span> <span data-ttu-id="03719-138">Al crear una configuración de trasvase de registros, puede controlar el comportamiento de la compresión de copia de seguridad de las copias de seguridad del registro eligiendo una de las opciones siguientes: **Usar la configuración de servidor predeterminada**, **Comprimir copia de seguridad** o **No comprimir copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="03719-138">When creating a log shipping configuration, you can control the backup compression behavior of log backups by choosing one of the following options: **Use the default server setting**, **Compress backup**, or **Do not compress backup**.</span></span> <span data-ttu-id="03719-139">Para obtener más información, consulte [Log Shipping Transaction Log Backup Settings](../../relational-databases/databases/log-shipping-transaction-log-backup-settings.md).</span><span class="sxs-lookup"><span data-stu-id="03719-139">For more information, see [Log Shipping Transaction Log Backup Settings](../../relational-databases/databases/log-shipping-transaction-log-backup-settings.md).</span></span>  
  
10. <span data-ttu-id="03719-140">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="03719-140">Click **OK**.</span></span>  
  
11. <span data-ttu-id="03719-141">En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="03719-141">Under **Secondary server instances and databases**, click **Add**.</span></span>  
  
12. <span data-ttu-id="03719-142">Haga clic en **Conectar** para conectarse a la sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que desee utilizar como servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="03719-142">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your secondary server.</span></span>  
  
13. <span data-ttu-id="03719-143">En el cuadro **Base de datos secundaria** , elija una base de datos de la lista o escriba el nombre de la base de datos que desea crear.</span><span class="sxs-lookup"><span data-stu-id="03719-143">In the **Secondary Database** box, choose a database from the list or type the name of the database you want to create.</span></span>  
  
14. <span data-ttu-id="03719-144">En la pestaña **Inicializar base de datos secundaria** , elija la opción que desee utilizar para inicializar la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="03719-144">On the **Initialize Secondary database** tab, choose the option that you want to use to initialize the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="03719-145">Si elige que [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] inicialice la base de datos secundaria desde una copia de seguridad de base de datos, los archivos de datos y de registro de la base de datos secundaria se colocan en la misma ubicación que los archivos de datos y de registro de la base de datos maestra ( **master** ).</span><span class="sxs-lookup"><span data-stu-id="03719-145">If you choose to have [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] initialize the secondary database from a database backup, the data and log files of the secondary database are placed in the same location as the data and log files of the **master** database.</span></span> <span data-ttu-id="03719-146">Es probable que esta ubicación sea diferente de la de los archivos de datos y de registro de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="03719-146">This location is likely to be different than the location of the data and log files of the primary database.</span></span>  
  
15. <span data-ttu-id="03719-147">En la pestaña **Copiar archivos** , en el cuadro **Carpeta de destino de los archivos copiados** , escriba la ruta de acceso de la carpeta en la que deben copiarse las copias de seguridad de los registros de transacciones.</span><span class="sxs-lookup"><span data-stu-id="03719-147">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="03719-148">Esta carpeta normalmente está situada en el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="03719-148">This folder is often located on the secondary server.</span></span>  
  
16. <span data-ttu-id="03719-149">Tenga presente la programación de copia que aparece en el cuadro **Programación** bajo **Trabajo de copia**.</span><span class="sxs-lookup"><span data-stu-id="03719-149">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="03719-150">Si desea personalizar la programación de su instalación, haga clic en **Programar** y, a continuación, ajuste la programación del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="03719-150">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="03719-151">El programa debe parecerse al de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="03719-151">This schedule should approximate the backup schedule.</span></span>  
  
17. <span data-ttu-id="03719-152">En la pestaña **Restaurar** , en **Estado de la base de datos al restaurar copias de seguridad**, elija la opción **Modo sin recuperación** o **Modo de espera** .</span><span class="sxs-lookup"><span data-stu-id="03719-152">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** or **Standby mode** option.</span></span>  
  
18. <span data-ttu-id="03719-153">Si elige la opción **Modo de espera** , seleccione si desea desconectar a los usuarios de la base de datos secundaria mientras se realiza la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="03719-153">If you chose the **Standby mode** option, choose if you want to disconnect users from the secondary database while the restore operation is underway.</span></span>  
  
19. <span data-ttu-id="03719-154">Si desea retrasar el proceso de restauración en el servidor secundario, elija un tiempo de retraso en **Retrasar la restauración de las copias de seguridad al menos**.</span><span class="sxs-lookup"><span data-stu-id="03719-154">If you want to delay the restore process on the secondary server, choose a delay time under **Delay restoring backups at least**.</span></span>  
  
20. <span data-ttu-id="03719-155">Elija un umbral de alerta en **Mostrar una alerta si no se produce una restauración tras**.</span><span class="sxs-lookup"><span data-stu-id="03719-155">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>  
  
21. <span data-ttu-id="03719-156">Tenga presente la programación de la restauración que aparece en el cuadro **Programación** bajo **Trabajo de restauración**.</span><span class="sxs-lookup"><span data-stu-id="03719-156">Note the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="03719-157">Si desea personalizar la programación de su instalación, haga clic en **Programar** y, a continuación, ajuste la programación del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="03719-157">If you want to customize the schedule for your installation, click **Schedule** and then adjust the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent schedule as needed.</span></span> <span data-ttu-id="03719-158">El programa debe parecerse al de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="03719-158">This schedule should approximate the backup schedule.</span></span>  
  
22. <span data-ttu-id="03719-159">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="03719-159">Click **OK**.</span></span>  
  
23. <span data-ttu-id="03719-160">En **Instancia del servidor de supervisión**, active la casilla **Utilizar una instancia del servidor de supervisión** y, a continuación, haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="03719-160">Under **Monitor server instance**, select the **Use a monitor server instance** check box, and then click **Settings**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="03719-161">Para supervisar esta configuración de trasvase de registros, debe agregar ahora el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="03719-161">To monitor this log shipping configuration, you must add the monitor server now.</span></span> <span data-ttu-id="03719-162">Para agregar un servidor de supervisión más adelante, deberá quitar esta configuración de trasvase de registros y reemplazarla por una configuración nueva que incluya un servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="03719-162">To add the monitor server later, you would need to remove this log shipping configuration and then replace it with a new configuration that includes a monitor server.</span></span>  
  
24. <span data-ttu-id="03719-163">Haga clic en **Conectar** y conéctese a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que desea utilizar como servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="03719-163">Click **Connect** and connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to use as your monitor server.</span></span>  
  
25. <span data-ttu-id="03719-164">En **Supervisar conexiones**, elija el método de conexión que utilizarán los trabajos de copia de seguridad, copia y restauración para conectarse al servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="03719-164">Under **Monitor connections**, choose the connection method to be used by the backup, copy, and restore jobs to connect to the monitor server.</span></span>  
  
26. <span data-ttu-id="03719-165">En **Retención de historial**, elija el período de tiempo que desea retener un registro del historial de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="03719-165">Under **History retention**, choose the length of time you want to retain a record of your log shipping history.</span></span>  
  
27. <span data-ttu-id="03719-166">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="03719-166">Click **OK**.</span></span>  
  
28. <span data-ttu-id="03719-167">En el cuadro de diálogo **Propiedades de la base de datos** , haga clic en **Aceptar** para comenzar el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="03719-167">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="03719-168">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03719-168">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-log-shipping"></a><span data-ttu-id="03719-169">Para configurar el trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="03719-169">To configure log shipping</span></span>  
  
1.  <span data-ttu-id="03719-170">Inicialice la base de datos secundaria restaurando una copia de seguridad completa de la base de datos principal en el servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="03719-170">Initialize the secondary database by restoring a full backup of the primary database on the secondary server.</span></span>  
  
2.  <span data-ttu-id="03719-171">En el servidor principal, ejecute [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql) para agregar una base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="03719-171">On the primary server, execute [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql) to add a primary database.</span></span> <span data-ttu-id="03719-172">El procedimiento almacenado devuelve el Id. de trabajo de la copia de seguridad y el Id. principal.</span><span class="sxs-lookup"><span data-stu-id="03719-172">The stored procedure returns the backup job ID and primary ID.</span></span>  
  
3.  <span data-ttu-id="03719-173">En el servidor principal, ejecute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) para agregar una programación para el trabajo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="03719-173">On the primary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to add a schedule for the backup job.</span></span>  
  
4.  <span data-ttu-id="03719-174">En el servidor de supervisión, ejecute [sp_add_log_shipping_alert_job](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-alert-job-transact-sql) para agregar el trabajo de alerta.</span><span class="sxs-lookup"><span data-stu-id="03719-174">On the monitor server, execute [sp_add_log_shipping_alert_job](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-alert-job-transact-sql) to add the alert job.</span></span>  
  
5.  <span data-ttu-id="03719-175">En el servidor principal, habilite el trabajo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="03719-175">On the primary server, enable the backup job.</span></span>  
  
6.  <span data-ttu-id="03719-176">En el servidor secundario, ejecute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) y proporcione los detalles del servidor y la base de datos principales.</span><span class="sxs-lookup"><span data-stu-id="03719-176">On the secondary server, execute [sp_add_log_shipping_secondary_primary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-primary-transact-sql) supplying the details of the primary server and database.</span></span> <span data-ttu-id="03719-177">Este procedimiento almacenado devuelve el Id. secundario y los Id. de los trabajos de copia y restauración.</span><span class="sxs-lookup"><span data-stu-id="03719-177">This stored procedure returns the secondary ID and the copy and restore job IDs.</span></span>  
  
7.  <span data-ttu-id="03719-178">En el servidor secundario, ejecute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) para establecer la programación de los trabajos de copia y restauración.</span><span class="sxs-lookup"><span data-stu-id="03719-178">On the secondary server, execute [sp_add_jobschedule](/sql/relational-databases/system-stored-procedures/sp-add-jobschedule-transact-sql) to set the schedule for the copy and restore jobs.</span></span>  
  
8.  <span data-ttu-id="03719-179">En el servidor secundario, ejecute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) para agregar una base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="03719-179">On the secondary server, execute [sp_add_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql) to add a secondary database.</span></span>  
  
9. <span data-ttu-id="03719-180">En el servidor principal, ejecute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) para agregar la información necesaria sobre la nueva base de datos secundaria al servidor principal.</span><span class="sxs-lookup"><span data-stu-id="03719-180">On the primary server, execute [sp_add_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-secondary-transact-sql) to add the required information about the new secondary database to the primary server.</span></span>  
  
10. <span data-ttu-id="03719-181">En el servidor secundario, habilite los trabajos de copia y restauración.</span><span class="sxs-lookup"><span data-stu-id="03719-181">On the secondary server, enable the copy and restore jobs.</span></span> <span data-ttu-id="03719-182">Para obtener más información, consulte [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="03719-182">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="03719-183">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="03719-183">Related Tasks</span></span>  
  
-   [<span data-ttu-id="03719-184">Actualizar el trasvase de registros a SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="03719-184">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="03719-185">Agregar una base de datos secundaria a la configuración de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="03719-185">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="03719-186">Quitar una base de datos secundaria desde una configuración de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="03719-186">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="03719-187">Quitar el trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="03719-187">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="03719-188">Ver el informe de trasvase de registros &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="03719-188">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="03719-189">Supervisar el trasvase de registros &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="03719-189">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="03719-190">Conmutar por error a una base de datos secundaria de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="03719-190">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="03719-191">Consulte también</span><span class="sxs-lookup"><span data-stu-id="03719-191">See Also</span></span>  
 <span data-ttu-id="03719-192">[Acerca del trasvase de registros &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="03719-192">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="03719-193">Tablas y procedimientos almacenados de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="03719-193">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
