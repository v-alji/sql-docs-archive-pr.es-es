---
title: Configuración de SQL Server copia de seguridad administrada en Azure | Microsoft Docs
ms.custom: ''
ms.date: 08/04/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 68ebb53e-d5ad-4622-af68-1e150b94516e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b9e3b86fde91028106263310aad8a1952fc041a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676517"
---
# <a name="setting-up-sql-server-managed-backup-to-azure"></a><span data-ttu-id="bc529-102">Configuración de copia de seguridad administrada de SQL Server en Azure</span><span class="sxs-lookup"><span data-stu-id="bc529-102">Setting up SQL Server Managed Backup to Azure</span></span>
  <span data-ttu-id="bc529-103">Este tema incluye dos tutoriales:</span><span class="sxs-lookup"><span data-stu-id="bc529-103">This topic includes two tutorials:</span></span>  
  
 <span data-ttu-id="bc529-104">Configurar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] en el nivel de base de datos, habilitar la notificación por correo electrónico y supervisar la actividad de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bc529-104">Set up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the database level, enable email notification, and monitor backup activity.</span></span>  
  
 <span data-ttu-id="bc529-105">Configurar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] en el nivel de instancia, habilitar la notificación por correo electrónico y supervisar la actividad de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bc529-105">Setting up  [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the instance level, enable email notification, and monitor backup activity.</span></span>  
  
 <span data-ttu-id="bc529-106">Para ver un tutorial sobre la configuración [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] de grupos de disponibilidad, consulte [configuración de SQL Server copia de seguridad administrada en Microsoft Azure para grupos de disponibilidad](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="bc529-106">For a tutorial on setting up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for Availability Groups, see [Setting up SQL Server Managed Backup to Microsoft Azure for Availability Groups](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
## <a name="setting-up-ss_smartbackup"></a><span data-ttu-id="bc529-107">Configurar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc529-107">Setting Up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]</span></span>  
  
### <a name="enable-and-configure-ss_smartbackup-for-a-database"></a><span data-ttu-id="bc529-108">Habilitar y configurar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] para una base de datos</span><span class="sxs-lookup"><span data-stu-id="bc529-108">Enable and Configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a Database</span></span>  
 <span data-ttu-id="bc529-109">En este tutorial se describen los pasos necesarios para habilitar y configurar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] para una base de datos (TestDB), además de los pasos para habilitar la supervisión del estado de mantenimiento de [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc529-109">This tutorial describes the steps necessary to enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a database (TestDB), followed by steps to enable monitoring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] health status.</span></span>  
  
 <span data-ttu-id="bc529-110">**Permisos:**</span><span class="sxs-lookup"><span data-stu-id="bc529-110">**Permissions:**</span></span>  
  
-   <span data-ttu-id="bc529-111">Requiere la pertenencia al rol de base de datos **db_backupoperator** , con permisos **ALTER any Credential** y `EXECUTE` permisos en **sp_delete_backuphistory**procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="bc529-111">Requires membership in **db_backupoperator** database role, with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on **sp_delete_backuphistory**stored procedure.</span></span>  
  
-   <span data-ttu-id="bc529-112">Requiere permisos **Select** en la función **smart_admin. fn_get_current_xevent_settings**.</span><span class="sxs-lookup"><span data-stu-id="bc529-112">Requires **SELECT** permissions on the **smart_admin.fn_get_current_xevent_settings**function.</span></span>  
  
-   <span data-ttu-id="bc529-113">Requiere `EXECUTE` permisos en el procedimiento almacenado **smart_admin. sp_get_backup_diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="bc529-113">Requires `EXECUTE` permissions on the **smart_admin.sp_get_backup_diagnostics** stored procedure.</span></span> <span data-ttu-id="bc529-114">Además, requiere permisos `VIEW SERVER STATE` ya que internamente llama a otros objetos del sistema que requieren este permiso.</span><span class="sxs-lookup"><span data-stu-id="bc529-114">In addition, it requires `VIEW SERVER STATE` permissions as it internally calls other system objects that require this permission.</span></span>  
  
-   <span data-ttu-id="bc529-115">Requiere `EXECUTE` permisos en los `smart_admin.sp_set_instance_backup` `smart_admin.sp_backup_master_switch` procedimientos almacenados y.</span><span class="sxs-lookup"><span data-stu-id="bc529-115">Requires `EXECUTE` permissions on the `smart_admin.sp_set_instance_backup` and `smart_admin.sp_backup_master_switch` stored procedures.</span></span>  


1.  <span data-ttu-id="bc529-116">**Cree una cuenta de almacenamiento de Microsoft Azure:** Las copias de seguridad se almacenan en el servicio de almacenamiento de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="bc529-116">**Create a Microsoft Azure storage account:** The backups are stored in the Microsoft Azure storage service.</span></span> <span data-ttu-id="bc529-117">En primer lugar, debe crear una cuenta de almacenamiento de Microsoft Azure, si aún no tiene una cuenta.</span><span class="sxs-lookup"><span data-stu-id="bc529-117">You must first create a Microsoft Azure storage account, if you do not already have an account.</span></span>
    - <span data-ttu-id="bc529-118">SQL Server 2014 usa blobs en páginas, que son diferentes de los blobs en bloques y anexos.</span><span class="sxs-lookup"><span data-stu-id="bc529-118">SQL Server 2014 uses page blobs, which are different than block and append blobs.</span></span> <span data-ttu-id="bc529-119">Por lo tanto, debe crear una cuenta de uso general y no una cuenta de BLOB.</span><span class="sxs-lookup"><span data-stu-id="bc529-119">Therefore you must create a general purpose account, and not a blob account.</span></span> <span data-ttu-id="bc529-120">Para más información, consulte [Acerca de las cuentas de almacenamiento de Azure](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span><span class="sxs-lookup"><span data-stu-id="bc529-120">For more information, see [About Azure storage accounts](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span></span>
    - <span data-ttu-id="bc529-121">Anote el nombre de la cuenta de almacenamiento y las claves de acceso.</span><span class="sxs-lookup"><span data-stu-id="bc529-121">Make a note of the storage account name, and the access keys.</span></span> <span data-ttu-id="bc529-122">La información del nombre de cuenta y de la clave de acceso se utiliza para crear una credencial SQL.</span><span class="sxs-lookup"><span data-stu-id="bc529-122">The storage account name and access key information is used to create a SQL Credential.</span></span> <span data-ttu-id="bc529-123">La credencial SQL se usa para autenticarse en la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="bc529-123">The SQL Credential is used to authenticate to the storage account.</span></span>  
 
2.  <span data-ttu-id="bc529-124">**Cree una credencial de SQL:** Cree una credencial de SQL con el nombre de la cuenta de almacenamiento como identidad y la clave de acceso de almacenamiento como contraseña.</span><span class="sxs-lookup"><span data-stu-id="bc529-124">**Create a SQL Credential:** Create a SQL Credential using the name of the storage account as the Identity and the storage access key as the password.</span></span>  
  
3.  <span data-ttu-id="bc529-125">**Asegúrese de que Agente SQL Server servicio se ha iniciado y está en ejecución:**  Inicie Agente SQL Server si no se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="bc529-125">**Ensure SQL Server Agent service is Started and Running:**  Start SQL Server Agent if it is not currently running.</span></span>  [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="bc529-126">requiere que el Agente SQL Server se ejecute en la instancia para realizar operaciones de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bc529-126">requires SQL Server Agent to be running on the instance to perform backup operations.</span></span>  <span data-ttu-id="bc529-127">Puede ser conveniente configurar el Agente SQL Server para que se ejecute automáticamente con el fin de asegurarse de que las operaciones de copia de seguridad pueden realizarse periódicamente.</span><span class="sxs-lookup"><span data-stu-id="bc529-127">You may want to set SQL Server Agent to run automatically to make sure that backup operations can occur regularly.</span></span>  
  
4.  <span data-ttu-id="bc529-128">**Determine el período de retención:** Determine el período de retención para los archivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bc529-128">**Determine the retention period:** Determine the retention period for the backup files.</span></span> <span data-ttu-id="bc529-129">El período de retención se especifica en días y puede abarcar de 1 a 30.</span><span class="sxs-lookup"><span data-stu-id="bc529-129">The retention period is specified in days and can range from 1 to 30.</span></span>  
  
5.  <span data-ttu-id="bc529-130">**Habilitar y configurar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** inicie SQL Server Management Studio y conéctese a la instancia donde está instalada la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bc529-130">**Enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Start SQL Server Management Studio and connect to the instance where the database is installed.</span></span> <span data-ttu-id="bc529-131">En la ventana de consulta, ejecute la siguiente instrucción después de modificar los valores correspondientes al nombre de la base de datos, la credencial SQL, el período de retención y las opciones de cifrado según sus requisitos:</span><span class="sxs-lookup"><span data-stu-id="bc529-131">From the query window run the following statement after you modify the values for the database name, SQL Credential, retention period, and encryption options per your requirements:</span></span>  
  
     <span data-ttu-id="bc529-132">Para obtener más información sobre la creación de un certificado para el cifrado, vea el paso **crear un certificado de copia** de seguridad en [creación de una copia de seguridad cifrada](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="bc529-132">For more information on creating a certificate for encryption, see the **Create a Backup Certificate** step in [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
    ```  
    Use msdb;  
    GO  
    EXEC smart_admin.sp_set_db_backup   
                    @database_name='TestDB'   
                    ,@retention_days=30   
                    ,@credential_name='MyCredential'  
                    ,@encryption_algorithm ='AES_128'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert'  
                    ,@enable_backup=1;  
    GO  
  
    ```  
  
     [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="bc529-133">está habilitada ahora en la base de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="bc529-133">is now enabled on the database you specified.</span></span> <span data-ttu-id="bc529-134">Puede tardarse hasta 15 minutos en que las operaciones de copia de seguridad de la base de datos empiecen a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="bc529-134">It may take up to 15 minutes for the backup operations on the database to start to run.</span></span>  
  
6.  <span data-ttu-id="bc529-135">**Revise la configuración predeterminada del evento extendido:** Revise la configuración de eventos extendidos ejecutando la siguiente instrucción transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="bc529-135">**Review Extended Event Default Configuration:** Review the Extended Event settings by running the following transact-SQL statement.</span></span>  
  
    ```  
    SELECT * FROM smart_admin.fn_get_current_xevent_settings()  
    ```  
  
     <span data-ttu-id="bc529-136">Debe ver que los eventos de canal Administración, Operativo y Analítico están habilitados de forma predeterminada y no se pueden deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="bc529-136">You should see that Admin, Operational, and Analytical channel events are enabled by default and cannot be disabled.</span></span> <span data-ttu-id="bc529-137">Debe ser suficiente supervisar los eventos que requieren intervención manual.</span><span class="sxs-lookup"><span data-stu-id="bc529-137">This should be sufficient to monitor the events that require manual intervention.</span></span>  <span data-ttu-id="bc529-138">Puede habilitar los eventos de depuración, pero los canales de depuración incluyen eventos informativos y de depuración que [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] usa para detectar problemas y solucionarlos.</span><span class="sxs-lookup"><span data-stu-id="bc529-138">You can enable debug events, but the debug channels include informational and debug events that [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] uses to detect issues and solve them.</span></span> <span data-ttu-id="bc529-139">Para obtener más información, vea [supervisar SQL Server copia de seguridad administrada en Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="bc529-139">For more information, see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
7.  <span data-ttu-id="bc529-140">**Habilite y configure la notificación del estado de mantenimiento:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] tiene un procedimiento almacenado que crea un trabajo del agente para enviar notificaciones por correo electrónico de los errores o las advertencias que puedan requerir atención.</span><span class="sxs-lookup"><span data-stu-id="bc529-140">**Enable and Configure Notification for Health Status:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] has a stored procedure that creates an agent job to send out e-mail notifications of errors or warnings that may require attention.</span></span> <span data-ttu-id="bc529-141">En los pasos siguientes se describe el proceso para habilitar y configurar las notificaciones por correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="bc529-141">The following steps describe the process to enable and configure e-mail notifications:</span></span>  
  
    1.  <span data-ttu-id="bc529-142">Configure Correo electrónico de base de datos si aún no está habilitado en la instancia.</span><span class="sxs-lookup"><span data-stu-id="bc529-142">Setup Database Mail if it is not already enabled on the instance.</span></span> <span data-ttu-id="bc529-143">Para obtener más información, vea [Configure Database Mail](../database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="bc529-143">For more information, see [Configure Database Mail](../database-mail/configure-database-mail.md).</span></span>  
  
    2.  <span data-ttu-id="bc529-144">Configure la notificación del Agente SQL Server para que use Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="bc529-144">Configure SQL Server Agent Notification to use Database Mail.</span></span> <span data-ttu-id="bc529-145">Para más información, consulte [Configurar el Agente SQL Server para que use el Correo electrónico de base de datos](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="bc529-145">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
    3.  <span data-ttu-id="bc529-146">**Habilite las notificaciones por correo electrónico para recibir advertencias y errores de copia de seguridad:** En la ventana de consulta, ejecute las siguientes instrucciones Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="bc529-146">**Enable e-mail notifications to receive backup errors and warnings:** From the query window, run the following Transact-SQL statements:</span></span>  
  
        ```  
        EXEC msdb.smart_admin.sp_set_parameter  
        @parameter_name = 'SSMBackup2WANotificationEmailIds',  
        @parameter_value = '<email1;email2>'  
  
        ```  
  
         <span data-ttu-id="bc529-147">Para obtener más información y un script de ejemplo completo, vea [Monitor SQL Server copia de seguridad administrada en Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="bc529-147">For more information, and a full sample script see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
8.  <span data-ttu-id="bc529-148">**Consulte los archivos de copia de seguridad en la cuenta de Azure Storage:** conéctese a la cuenta de almacenamiento desde SQL Server Management Studio o desde el Portal de administración de Azure.</span><span class="sxs-lookup"><span data-stu-id="bc529-148">**View backup files in the Microsoft Azure Storage Account:** Connect to the storage account from SQL Server Management Studio or the Azure Management Portal.</span></span> <span data-ttu-id="bc529-149">Verá un contenedor para la instancia de SQL Server que hospeda la base de datos que configuró para utilizar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc529-149">You will see a container for the instance of SQL Server that hosts the database you configured to use [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="bc529-150">También puede ver una base de datos y una copia de seguridad de registros antes de 15 minutos después de habilitar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bc529-150">You may also see a database and a log backup within 15 minutes of enabling [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the database.</span></span>  
  
9. <span data-ttu-id="bc529-151">**Supervise el estado de mantenimiento:**  puede supervisar a través de notificaciones por correo electrónico que ha configurado previamente, o bien supervisar los eventos registrados de forma activa.</span><span class="sxs-lookup"><span data-stu-id="bc529-151">**Monitor the Health Status:**  You can monitor through e-mail notifications you configured previously, or actively monitor the events logged.</span></span> <span data-ttu-id="bc529-152">Las siguientes son algunas instrucciones de Transact-SQL de ejemplo que se utilizan para ver los eventos:</span><span class="sxs-lookup"><span data-stu-id="bc529-152">The following are some example Transact-SQL Statements used to view the events:</span></span>  
  
    ```  
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
  
    ```  
    -- to enable debug events  
    Use msdb;  
    Go  
             EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
  
    ```  
  
    ```  
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;  
  
    ```  
  
 <span data-ttu-id="bc529-153">Los pasos descritos en esta sección son específicos para configurar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] por primera vez en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bc529-153">The steps described in this section are specifically for configuring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the first time on the database.</span></span> <span data-ttu-id="bc529-154">Puede modificar las configuraciones existentes mediante el mismo procedimiento almacenado del sistema **smart_admin. sp_set_db_backup** y proporcionar los nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="bc529-154">You can modify the existing configurations using the same system stored procedure **smart_admin.sp_set_db_backup** and provide the new values.</span></span> <span data-ttu-id="bc529-155">Para obtener más información, vea [SQL Server la copia de seguridad administrada en la configuración de retención y almacenamiento de Microsoft Azure](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md).</span><span class="sxs-lookup"><span data-stu-id="bc529-155">For more information, see [SQL Server Managed Backup to Microsoft Azure - Retention and Storage Settings](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md).</span></span>  
  
### <a name="enable-ss_smartbackup-for-the-instance-with-default-settings"></a><span data-ttu-id="bc529-156">Habilitar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] para la instancia con la configuración predeterminada</span><span class="sxs-lookup"><span data-stu-id="bc529-156">Enable [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the Instance with Default Settings</span></span>  
 <span data-ttu-id="bc529-157">En este tutorial se describen los pasos para habilitar y configurar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] para la instancia de, ' instanceof ', \\ .</span><span class="sxs-lookup"><span data-stu-id="bc529-157">This tutorial describes the steps to enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the instance, 'MyInstance',\\.</span></span> <span data-ttu-id="bc529-158">Incluye pasos para habilitar la supervisión del estado de mantenimiento de [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc529-158">It includes steps to enable monitoring the [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] health status.</span></span>  
  
 <span data-ttu-id="bc529-159">**Permisos:**</span><span class="sxs-lookup"><span data-stu-id="bc529-159">**Permissions:**</span></span>  
  
-   <span data-ttu-id="bc529-160">Requiere la pertenencia al rol de base de datos **db_backupoperator** , con permisos **ALTER any Credential** y `EXECUTE` permisos en **sp_delete_backuphistory**procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="bc529-160">Requires membership in **db_backupoperator** database role, with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on **sp_delete_backuphistory**stored procedure.</span></span>  
  
-   <span data-ttu-id="bc529-161">Requiere permisos **Select** en la función **smart_admin. fn_get_current_xevent_settings**.</span><span class="sxs-lookup"><span data-stu-id="bc529-161">Requires **SELECT** permissions on the **smart_admin.fn_get_current_xevent_settings**function.</span></span>  
  
-   <span data-ttu-id="bc529-162">Requiere `EXECUTE` permisos en el procedimiento almacenado **smart_admin. sp_get_backup_diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="bc529-162">Requires `EXECUTE` permissions on the **smart_admin.sp_get_backup_diagnostics** stored procedure.</span></span> <span data-ttu-id="bc529-163">Además, requiere permisos `VIEW SERVER STATE` ya que internamente llama a otros objetos del sistema que requieren este permiso.</span><span class="sxs-lookup"><span data-stu-id="bc529-163">In addition, it requires `VIEW SERVER STATE` permissions as it internally calls other system objects that require this permission.</span></span>  


1.  <span data-ttu-id="bc529-164">**Cree una cuenta de almacenamiento de Microsoft Azure:** Las copias de seguridad se almacenan en el servicio de almacenamiento de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="bc529-164">**Create a Microsoft Azure storage account:** The backups are stored in the Microsoft Azure storage service.</span></span> <span data-ttu-id="bc529-165">En primer lugar, debe crear una cuenta de almacenamiento de Microsoft Azure, si aún no tiene una cuenta.</span><span class="sxs-lookup"><span data-stu-id="bc529-165">You must first create a Microsoft Azure storage account, if you do not already have an account.</span></span>
    - <span data-ttu-id="bc529-166">SQL Server 2014 usa blobs en páginas, que son diferentes de los blobs en bloques y anexos.</span><span class="sxs-lookup"><span data-stu-id="bc529-166">SQL Server 2014 uses page blobs, which are different than block and append blobs.</span></span> <span data-ttu-id="bc529-167">Por lo tanto, debe crear una cuenta de uso general y no una cuenta de BLOB.</span><span class="sxs-lookup"><span data-stu-id="bc529-167">Therefore you must create a general purpose account, and not a blob account.</span></span> <span data-ttu-id="bc529-168">Para más información, consulte [Acerca de las cuentas de almacenamiento de Azure](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span><span class="sxs-lookup"><span data-stu-id="bc529-168">For more information, see [About Azure storage accounts](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span></span>
    - <span data-ttu-id="bc529-169">Anote el nombre de la cuenta de almacenamiento y las claves de acceso.</span><span class="sxs-lookup"><span data-stu-id="bc529-169">Make a note of the storage account name, and the access keys.</span></span> <span data-ttu-id="bc529-170">La información del nombre de cuenta y de la clave de acceso se utiliza para crear una credencial SQL.</span><span class="sxs-lookup"><span data-stu-id="bc529-170">The storage account name and access key information is used to create a SQL Credential.</span></span> <span data-ttu-id="bc529-171">La credencial SQL se usa para autenticarse en la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="bc529-171">The SQL Credential is used to authenticate to the storage account.</span></span>  
  
2.  <span data-ttu-id="bc529-172">**Cree una credencial de SQL:** Cree una credencial de SQL con el nombre de la cuenta de almacenamiento como identidad y la clave de acceso de almacenamiento como contraseña.</span><span class="sxs-lookup"><span data-stu-id="bc529-172">**Create a SQL Credential:** Create a SQL Credential using the name of the storage account as the Identity and the storage access key as the password.</span></span>  
  
3.  <span data-ttu-id="bc529-173">**Asegúrese de que el servicio del Agente SQL Server está iniciado y en ejecutándose:** inicie el Agente SQL Server si no se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="bc529-173">**Ensure SQL Server Agent service is Started and Running:** Start SQL Server Agent if it is not currently running.</span></span> [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="bc529-174">requiere que el Agente SQL Server se ejecute en la instancia para realizar operaciones de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bc529-174">requires SQL Server Agent to be running on the instance to perform backup operations.</span></span>  <span data-ttu-id="bc529-175">Puede ser conveniente configurar el Agente SQL Server para que se ejecute automáticamente con el fin de asegurarse de que las operaciones de copia de seguridad pueden realizarse periódicamente.</span><span class="sxs-lookup"><span data-stu-id="bc529-175">You may want to set SQL Server Agent to run automatically to make sure that backup operations can occur regularly.</span></span>  
  
4.  <span data-ttu-id="bc529-176">**Determine el período de retención:** Determine el período de retención para los archivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bc529-176">**Determine the retention period:** Determine the retention period for the backup files.</span></span> <span data-ttu-id="bc529-177">El período de retención se especifica en días y puede abarcar de 1 a 30.</span><span class="sxs-lookup"><span data-stu-id="bc529-177">The retention period is specified in days and can range from 1 to 30.</span></span> <span data-ttu-id="bc529-178">Una vez que [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] esté habilitada en el nivel de instancia con los valores predeterminados, todas las nuevas bases de datos creadas posteriormente heredarán los valores.</span><span class="sxs-lookup"><span data-stu-id="bc529-178">Once [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] is enabled at the instance level with the defaults all new databases created thereafter will inherit the settings.</span></span> <span data-ttu-id="bc529-179">Solo se admiten y se configurarán automáticamente las bases de datos configuradas para los modelos de recuperación completo u optimizado para cargas masivas de registro.</span><span class="sxs-lookup"><span data-stu-id="bc529-179">Only databases that are set to full or bulk-logged recovery models are supported and will be configured automatically.</span></span> <span data-ttu-id="bc529-180">Puede deshabilitar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] para una base de datos específica en cualquier momento si no desea que se configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc529-180">You may disable [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a specific database at any time if you  do not want [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] configured.</span></span> <span data-ttu-id="bc529-181">También puede cambiar la configuración de una base de datos específica configurando [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] en el nivel de base de datos.</span><span class="sxs-lookup"><span data-stu-id="bc529-181">You can also change the configuration for a specific database by configuring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the database level.</span></span>  
  
5.  <span data-ttu-id="bc529-182">**Habilitar y configurar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** inicie SQL Server Management Studio y conéctese a la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bc529-182">**Enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Start SQL Server Management Studio and connect to the instance of SQL Server.</span></span> <span data-ttu-id="bc529-183">En la ventana de consulta, ejecute la siguiente instrucción después de modificar los valores correspondientes al nombre de la base de datos, la credencial SQL, el período de retención y las opciones de cifrado según sus requisitos:</span><span class="sxs-lookup"><span data-stu-id="bc529-183">From the query window run the following statement after you modify the values for the database name, SQL Credential, retention period, and the encryption options per your requirements:</span></span>  
  
     <span data-ttu-id="bc529-184">Para obtener más información sobre la creación de un certificado para el cifrado, vea el paso **crear un certificado de copia** de seguridad en [creación de una copia de seguridad cifrada](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="bc529-184">For more information on creating a certificate for encryption, see the **Create a Backup Certificate** step in [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
    ```  
    Use msdb;  
    Go  
       EXEC smart_admin.sp_set_instance_backup  
                     @enable_backup=1  
                    ,@retention_days=30   
                    ,@credential_name='sqlbackuptoURL'  
                    ,@encryption_algorithm ='AES_128'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert';  
    GO  
  
    ```  
  
     [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="bc529-185">está habilitada ahora en la instancia.</span><span class="sxs-lookup"><span data-stu-id="bc529-185">is now enabled on the instance.</span></span>  
  
6.  <span data-ttu-id="bc529-186">Comprobar la configuración ejecutando la siguiente instrucción Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="bc529-186">Verify the configuration settings by running the following Transact-SQL statement:</span></span>  
  
    ```  
    Use msdb;  
    GO  
    SELECT * FROM smart_admin.fn_backup_instance_config ();  
  
    ```  
  
7.  <span data-ttu-id="bc529-187">Crear una nueva base de datos en la instancia.</span><span class="sxs-lookup"><span data-stu-id="bc529-187">Create a new database on the instance.</span></span> <span data-ttu-id="bc529-188">Ejecute la siguiente instrucción Transact-SQL para ver la configuración de [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] para la base de datos:</span><span class="sxs-lookup"><span data-stu-id="bc529-188">Run the following Transact-SQL statement to view the [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] configuration settings for the database:</span></span>  
  
    ```  
    Use msdb  
    GO  
    SELECT * FROM smart_admin.fn_backup_db_config('NewDB')  
    ```  
  
     <span data-ttu-id="bc529-189">Puede tardarse hasta 15 minutos en mostrarse la configuración y en que las operaciones de copia de seguridad de la base de datos empiecen a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="bc529-189">It may take up to 15 minutes for the settings to show and backup operations on the database to start to run.</span></span>  
  
8.  <span data-ttu-id="bc529-190">**Habilite y configure la notificación del estado de mantenimiento:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] tiene un procedimiento almacenado que crea un trabajo del agente para enviar notificaciones por correo electrónico de los errores o las advertencias que puedan requerir atención.</span><span class="sxs-lookup"><span data-stu-id="bc529-190">**Enable and Configure Notification for Health Status:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] has a stored procedure that creates an agent job to send out e-mail notifications of errors or warnings that may require attention.</span></span>  <span data-ttu-id="bc529-191">Para recibir dichas notificaciones, debe habilitar el procedimiento almacenado que crea un trabajo del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bc529-191">To receive such notifications, you must enable run the stored procedure which creates a SQL Server Agent Job.</span></span> <span data-ttu-id="bc529-192">En los pasos siguientes se describe el proceso para habilitar y configurar las notificaciones por correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="bc529-192">The following steps describe the process to enable and configure e-mail notifications:</span></span>  
  
    1.  <span data-ttu-id="bc529-193">Configure Correo electrónico de base de datos si aún no está habilitado en la instancia.</span><span class="sxs-lookup"><span data-stu-id="bc529-193">Setup Database Mail if it is not already enabled on the instance.</span></span> <span data-ttu-id="bc529-194">Para obtener más información, vea [Configure Database Mail](../database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="bc529-194">For more information, see [Configure Database Mail](../database-mail/configure-database-mail.md).</span></span>  
  
    2.  <span data-ttu-id="bc529-195">Configure la notificación del Agente SQL Server para que use Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="bc529-195">Configure SQL Server Agent Notification to use Database Mail.</span></span> <span data-ttu-id="bc529-196">Para más información, consulte [Configurar el Agente SQL Server para que use el Correo electrónico de base de datos](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="bc529-196">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
    3.  <span data-ttu-id="bc529-197">**Habilite las notificaciones por correo electrónico para recibir advertencias y errores de copia de seguridad:** En la ventana de consulta, ejecute las siguientes instrucciones Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="bc529-197">**Enable e-mail notifications to receive backup errors and warnings:** From the query window, run the following Transact-SQL statements:</span></span>  
  
        ```  
        EXEC msdb.smart_admin.sp_set_parameter  
        @parameter_name = 'SSMBackup2WANotificationEmailIds',  
        @parameter_value = '<email address>'  
  
        ```  
  
         <span data-ttu-id="bc529-198">Para obtener más información acerca de cómo supervisar y un script de ejemplo completo, vea [monitor SQL Server copia de seguridad administrada en Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="bc529-198">For more information about how to monitor, and a full sample script see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
9. <span data-ttu-id="bc529-199">**Consulte los archivos de copia de seguridad en la cuenta de Azure Storage:** conéctese a la cuenta de almacenamiento desde SQL Server Management Studio o desde el Portal de administración de Azure.</span><span class="sxs-lookup"><span data-stu-id="bc529-199">**View backup files in the Microsoft Azure Storage Account:** Connect to the storage account from SQL Server Management Studio or the Azure Management Portal.</span></span> <span data-ttu-id="bc529-200">Verá un contenedor para la instancia de SQL Server que hospeda la base de datos que configuró para utilizar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc529-200">You will see a container for the instance of SQL Server that hosts the database you configured to use [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="bc529-201">También puede ver una base de datos y una copia de seguridad de registros antes de 15 minutos después de crear una nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="bc529-201">You may also see a database and a log backup within 15 minutes of creating a new database.</span></span>  
  
10. <span data-ttu-id="bc529-202">**Supervise el estado de mantenimiento:**  puede supervisar a través de notificaciones por correo electrónico que ha configurado previamente, o bien supervisar los eventos registrados de forma activa.</span><span class="sxs-lookup"><span data-stu-id="bc529-202">**Monitor the Health Status:**  You can monitor through e-mail notifications you configured previously, or actively monitor the events logged.</span></span> <span data-ttu-id="bc529-203">Las siguientes son algunas instrucciones de Transact-SQL de ejemplo que se utilizan para ver los eventos:</span><span class="sxs-lookup"><span data-stu-id="bc529-203">The following are some example Transact-SQL Statements used to view the events:</span></span>  
  
    ```  
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
  
    ```  
    --  to enable debug events  
    Use msdb;  
    Go  
             EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
  
    ```  
  
    ```  
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;  
  
    ```  
  
 <span data-ttu-id="bc529-204">La configuración predeterminada de [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] se puede invalidar en una base de datos específica configurando los valores específicamente en el nivel de base de datos.</span><span class="sxs-lookup"><span data-stu-id="bc529-204">[!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] default settings can be overridden for a specific database by configuring the settings specifically at the database level.</span></span> <span data-ttu-id="bc529-205">También puede pausar y reanudar el servicio de [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] de forma temporal.</span><span class="sxs-lookup"><span data-stu-id="bc529-205">You can also pause and resume [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] service temporarily.</span></span> <span data-ttu-id="bc529-206">Para obtener más información, vea [SQL Server copia de seguridad administrada en Microsoft Azure-configuración de retención y almacenamiento](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md) .</span><span class="sxs-lookup"><span data-stu-id="bc529-206">For more information, see [SQL Server Managed Backup to Microsoft Azure - Retention and Storage Settings](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md)</span></span>  
  
  
