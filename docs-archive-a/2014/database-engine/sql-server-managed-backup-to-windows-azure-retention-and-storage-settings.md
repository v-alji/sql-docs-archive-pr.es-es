---
title: 'SQL Server de la copia de seguridad administrada en Azure: configuración de retención y almacenamiento | Microsoft Docs'
description: En este tema se describe cómo configurar SQL Server copia de seguridad administrada en Microsoft Azure para una base de datos y configurar las opciones predeterminadas de la instancia.
ms.custom: ''
ms.date: 08/23/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: c4aa26ea-5465-40cc-8b83-f50603cb9db1
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8ebdb81f8aa9edb9cd9326bcb1d286d5d3fe632c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748244"
---
# <a name="sql-server-managed-backup-to-azure---retention-and-storage-settings"></a><span data-ttu-id="6792c-103">Copia de seguridad administrada de SQL Server en Azure: configuración de la retención y el almacenamiento</span><span class="sxs-lookup"><span data-stu-id="6792c-103">SQL Server Managed Backup to Azure - Retention and Storage Settings</span></span>
  <span data-ttu-id="6792c-104">En este tema se describen los pasos básicos para configurar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para una base de datos y configurar las opciones predeterminadas de la instancia.</span><span class="sxs-lookup"><span data-stu-id="6792c-104">This topic describes the basic steps to configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a database and to configure default settings for the instance.</span></span> <span data-ttu-id="6792c-105">En el tema también se describen los pasos necesarios para pausar y reanudar los servicios de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] de la instancia.</span><span class="sxs-lookup"><span data-stu-id="6792c-105">The topic also describes the steps necessary to pause and resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services for the instance.</span></span>  
  
 <span data-ttu-id="6792c-106">Para ver un tutorial completo sobre la configuración [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] , consulte [configuración de SQL Server copia de seguridad administrada en Azure](../relational-databases/backup-restore/enable-sql-server-managed-backup-to-microsoft-azure.md) y [configuración de SQL Server copia de seguridad administrada en Azure para grupos de disponibilidad](../../2014/database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="6792c-106">For a complete walkthrough of setting up [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] see [Setting up SQL Server Managed Backup to Azure](../relational-databases/backup-restore/enable-sql-server-managed-backup-to-microsoft-azure.md) and [Setting up SQL Server Managed Backup to Azure for Availability Groups](../../2014/database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6792c-107">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6792c-107">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6792c-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="6792c-108">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6792c-109">No habilite [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] en las bases de datos que usen actualmente planes de mantenimiento o el trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="6792c-109">Do not enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on databases that are currently using maintenance plans or log shipping.</span></span> <span data-ttu-id="6792c-110">Para obtener más información sobre la interoperabilidad y coexistencia con otras características de SQL Server, consulte [SQL Server copia de seguridad administrada en Azure: interoperabilidad y coexistencia](../../2014/database-engine/sql-server-managed-backup-to-windows-azure-interoperability-and-coexistence.md)</span><span class="sxs-lookup"><span data-stu-id="6792c-110">For more information on interoperability and coexistence with other SQL Server features, see [SQL Server Managed Backup to Azure: Interoperability and Coexistence](../../2014/database-engine/sql-server-managed-backup-to-windows-azure-interoperability-and-coexistence.md)</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6792c-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6792c-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="6792c-112">El Agente SQL Server debe estar ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="6792c-112">SQL Server Agent should be running.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="6792c-113">Si el Agente SQL Server se detiene durante un período de tiempo y después se reinicia, es posible que observe un incremento en la actividad de copia de seguridad en función del tiempo que transcurrió entre la detención y el inicio del Agente SQL Server y puede que haya copias de seguridad de registros pendientes en espera de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6792c-113">If SQL Server Agent is stopped for a period of time and then restarted, you may see an increased backup activity depending on the length of time elapsed between the stop and start of SQL Agent, and there might be a backlog of log backups waiting to run.</span></span> <span data-ttu-id="6792c-114">Se recomienda configurar un Agente SQL Server que se inicie de forma automática en el arranque.</span><span class="sxs-lookup"><span data-stu-id="6792c-114">Consider configuring SQL Server Agent to start automatically on start up.</span></span>  
  
-   <span data-ttu-id="6792c-115">Antes de configurar, debe crearse una cuenta de almacenamiento de Azure y una credencial SQL que almacene la información de autenticación en la cuenta de almacenamiento [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6792c-115">A Azure storage account and a SQL Credential that stores the authentication information to the storage account should both be created before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="6792c-116">Para obtener más información, consulte la sección [Introduction to Key Components and Concepts](../relational-databases/backup-restore/sql-server-backup-to-url.md#intorkeyconcepts) del tema **Copiar de seguridad de SQL Server a URL** y [Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="6792c-116">For more information see [Introduction to Key Components and Concepts](../relational-databases/backup-restore/sql-server-backup-to-url.md#intorkeyconcepts) section of the **SQL Server Backup to URL** topic, and [Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
    > [!IMPORTANT]  
    >  [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="6792c-117">crea los contenedores necesarios para almacenar las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6792c-117">creates the necessary containers to store the backups.</span></span> <span data-ttu-id="6792c-118">El nombre del contenedor se crea con el formato ' nombre de equipo-nombre de instancia '.</span><span class="sxs-lookup"><span data-stu-id="6792c-118">The container name is created using 'machine name-instance name' format.</span></span> <span data-ttu-id="6792c-119">Para los Grupos de disponibilidad AlwayOn, el contenedor se denomina con el GUID del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="6792c-119">For AlwaysOn Availability Groups the container is named using the GUID of the availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6792c-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6792c-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6792c-121">Permisos</span><span class="sxs-lookup"><span data-stu-id="6792c-121">Permissions</span></span>  
 <span data-ttu-id="6792c-122">Para ejecutar los procedimientos almacenados que habilitan [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] , debe ser un `System Administrator` miembro o en el rol de base de datos **Db_backupoperator** con permisos **ALTER any Credential** , y `EXECUTE` permisos en el **sp_delete_backuphistory**y `smart_admin.sp_backup_master_switch` procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="6792c-122">To run the stored procedures that enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], you must be a  either a `System Administrator` or  member  in the **db_backupoperator** database role with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on the **sp_delete_backuphistory**, and `smart_admin.sp_backup_master_switch` stored procedures.</span></span>  <span data-ttu-id="6792c-123">Los procedimientos almacenados y las funciones que se usan para revisar la configuración existente normalmente requieren permisos `Execute` en el procedimiento almacenado y `Select` en la función, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6792c-123">Stored procedures and functions used to review the existing settings typically require `Execute` permissions on the stored procedure and `Select` on the function respectively.</span></span>  
  

  
###  <a name="considerations-for-enabling-ss_smartbackup-for-databases-and-instances"></a><a name="Considerations"></a><span data-ttu-id="6792c-124">Consideraciones para habilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para las bases de datos y las instancias</span><span class="sxs-lookup"><span data-stu-id="6792c-124">Considerations for enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for Databases and Instances</span></span>  
 [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="6792c-125">se puede habilitar para las bases de datos individuales por separado o para toda la instancia.</span><span class="sxs-lookup"><span data-stu-id="6792c-125">can be enabled for individual databases separately or for the entire instance.</span></span> <span data-ttu-id="6792c-126">Las opciones dependen de los requisitos de capacidad de recuperación de las bases de datos de la instancia, los requisitos para administrar varias bases de datos y las instancias, y el uso estratégico del almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="6792c-126">The choices depend on the recoverability requirements for the databases on the instance, requirements for managing multiple databases and instances, and using Azure storage strategically.</span></span>  
  
#### <a name="enabling-ss_smartbackup-at-the-database-level"></a><span data-ttu-id="6792c-127">Habilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] en el nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="6792c-127">Enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Database Level</span></span>  
 <span data-ttu-id="6792c-128">Si una base de datos tiene requisitos concretos para el periodo de retención (la capacidad de recuperación SLA) y la copia de seguridad diferentes de otras bases de datos de la instancia, configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] en el nivel de base de datos para esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="6792c-128">If a database has specific requirements for backup and retention period (recoverability SLA) that is different from other databases on the instance, configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the database level for this database.</span></span> <span data-ttu-id="6792c-129">La configuración en el nivel de base de datos invalida la configuración en el nivel de instancia.</span><span class="sxs-lookup"><span data-stu-id="6792c-129">Database level settings override instance level configuration settings.</span></span> <span data-ttu-id="6792c-130">Sin embargo, ambas opciones se pueden utilizar conjuntamente en la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="6792c-130">However both these options can be used together on the same instance.</span></span> <span data-ttu-id="6792c-131">La siguiente es una lista de ventajas y de consideraciones al habilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] en el nivel de base de datos.</span><span class="sxs-lookup"><span data-stu-id="6792c-131">Following is a list of advantages and considerations when enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the database level.</span></span>  
  
-   <span data-ttu-id="6792c-132">Más específico: opciones de configuración independientes para cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="6792c-132">More granular: Separate configuration settings for each database.</span></span> <span data-ttu-id="6792c-133">Puede admitir periodos de retención diferentes para bases de datos individuales.</span><span class="sxs-lookup"><span data-stu-id="6792c-133">Can support different retention periods for individual databases.</span></span>  
  
-   <span data-ttu-id="6792c-134">Invalida los valores de nivel de instancia para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6792c-134">Overrides instance level settings for the database.</span></span>  
  
-   <span data-ttu-id="6792c-135">Se puede utilizar para reducir los costos de almacenamiento seleccionando las bases de datos individuales cuya copia de seguridad se va a realizar.</span><span class="sxs-lookup"><span data-stu-id="6792c-135">Can be used to reduce storage costs by selecting individual databases to be backed up.</span></span>  
  
-   <span data-ttu-id="6792c-136">Requiere administrar cada base de datos</span><span class="sxs-lookup"><span data-stu-id="6792c-136">Requires managing each database</span></span>  
  
#### <a name="enabling-ss_smartbackup-at-the-instance-level-with-default-settings"></a><span data-ttu-id="6792c-137">Habilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] en el nivel de instancia con la configuración predeterminada</span><span class="sxs-lookup"><span data-stu-id="6792c-137">Enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Instance Level with Default Settings</span></span>  
 <span data-ttu-id="6792c-138">Utilice esta configuración si la mayoría de las bases de datos de la instancia tiene los mismos requisitos para las directivas de retención y copia de seguridad o si desea realizar la copia de seguridad de las nuevas instancias de base de datos automáticamente tras su creación.</span><span class="sxs-lookup"><span data-stu-id="6792c-138">Use this setting if most of the databases in the instance have the same requirements for backup and retention policies, or if you want new database instances to automatically be backed up on creation.</span></span> <span data-ttu-id="6792c-139">Algunas bases de datos que constituyen la excepción de la directiva todavía se pueden configurar individualmente.</span><span class="sxs-lookup"><span data-stu-id="6792c-139">A few databases that are exception to the policy can still be configured individually.</span></span> <span data-ttu-id="6792c-140">A continuación se muestra una lista de ventajas y consideraciones a la hora de habilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] en el nivel de instancia.</span><span class="sxs-lookup"><span data-stu-id="6792c-140">Following is a list of advantages and considerations when enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the instance level.</span></span>  
  
-   <span data-ttu-id="6792c-141">Automatización en el nivel de instancia: se aplica automáticamente una configuración común a las nuevas bases de datos agregadas posteriormente.</span><span class="sxs-lookup"><span data-stu-id="6792c-141">Automation at the instance level: Common settings applied to automatically for new databases added thereafter.</span></span>  
  
-   <span data-ttu-id="6792c-142">La copia de seguridad de las nuevas bases de datos se realiza automáticamente en cuanto se crean en las instancias</span><span class="sxs-lookup"><span data-stu-id="6792c-142">New databases will be automatically backed up soon after they are created on the instances</span></span>  
  
-   <span data-ttu-id="6792c-143">Puede aplicarse a las bases de datos que tienen los mismos requisitos del período de retención.</span><span class="sxs-lookup"><span data-stu-id="6792c-143">Can be applied to databases that have the same retention period requirements.</span></span>  
  
-   <span data-ttu-id="6792c-144">Todavía puede configurar bases de datos individuales que requieren otro periodo de retención diferente incluso con la copia de seguridad de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] habilitada en el nivel de instancia con la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6792c-144">You can still configure individual databases that require a different retention period even with [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] backup enabled at in instance level with default settings.</span></span> <span data-ttu-id="6792c-145">También puede deshabilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para las bases de datos si no pretende usar Azure Storage para las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6792c-145">You can also disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for databases if you do not intend to use Azure storage for the backups.</span></span>  
  
##  <a name="enable-and-configure-ss_smartbackup-for-a-database"></a><a name="DatabaseConfigure"></a><span data-ttu-id="6792c-146">Habilitar y configurar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para una base de datos</span><span class="sxs-lookup"><span data-stu-id="6792c-146">Enable and Configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a Database</span></span>  
 <span data-ttu-id="6792c-147">El procedimiento almacenado del sistema `smart_admin.sp_set_db_backup` se utiliza para habilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para una base de datos específica.</span><span class="sxs-lookup"><span data-stu-id="6792c-147">The system stored procedure `smart_admin.sp_set_db_backup` is used to enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a specific database.</span></span> <span data-ttu-id="6792c-148">Cuando [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] se habilita por primera vez en la base de datos, la siguiente información se debe especificar además de habilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6792c-148">When [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the first time on the database, the following information must be specified in addition to enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]:</span></span>  
  
-   <span data-ttu-id="6792c-149">El nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6792c-149">The name of the database.</span></span>  
  
-   <span data-ttu-id="6792c-150">El período de retención.</span><span class="sxs-lookup"><span data-stu-id="6792c-150">The retention period.</span></span>  
  
-   <span data-ttu-id="6792c-151">Credencial SQL usada para autenticarse en la cuenta de almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="6792c-151">SQL Credential used to authenticate to the Azure storage account.</span></span>  
  
-   <span data-ttu-id="6792c-152">Especifique que no se cifre mediante \* \@ encryption_algorithm\*  =  **NO_ENCRYPTION** o especifique un algoritmo de cifrado admitido.</span><span class="sxs-lookup"><span data-stu-id="6792c-152">Either specify not to encrypt using *\@encryption_algorithm* = **NO_ENCRYPTION** or specify a supported encryption algorithm.</span></span> <span data-ttu-id="6792c-153">Para obtener más información sobre cifrado, vea [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="6792c-153">For more information on encryption, see [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span></span>  
  
 [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="6792c-154">para la configuración del nivel de base de datos solo se admite con Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="6792c-154">for database level configuration is only supported through Transact-SQL.</span></span>  
  
 <span data-ttu-id="6792c-155">Una vez que [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] está habilitada para una base de datos, esta información se conserva.</span><span class="sxs-lookup"><span data-stu-id="6792c-155">Once [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for a database this information is persisted.</span></span> <span data-ttu-id="6792c-156">Si va a cambiar la configuración, solo se requiere el nombre de la base de datos y el valor que desea cambiar, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] retiene los valores existentes para los otros parámetros cuando no se especifiquen.</span><span class="sxs-lookup"><span data-stu-id="6792c-156">If you are changing the configuration, only the database name and the setting you want to change is required, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] retains the existing values for other parameters when not specified.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6792c-157">Antes de configurar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] en una base de datos puede ser útil para la configuración existente.</span><span class="sxs-lookup"><span data-stu-id="6792c-157">Before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on a database it might be useful to existing configuration if any.</span></span> <span data-ttu-id="6792c-158">El paso para revisar la configuración de una base de datos se describe más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="6792c-158">The step to reviewing configuration settings for a database is explained later in this section.</span></span>  
  
-   <span data-ttu-id="6792c-159">**Usar Transact-SQL:**</span><span class="sxs-lookup"><span data-stu-id="6792c-159">**Using Transact-SQL:**</span></span>  
  
     <span data-ttu-id="6792c-160">Si va a habilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] por primera vez, los parámetros necesarios son: \* \@ database_name*, \* \@ credential_name* \* \@ encryption_algorithm*, \* \@ enable_backup* el parámetro \* \@ storage_url\* es opcional.</span><span class="sxs-lookup"><span data-stu-id="6792c-160">If you are enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for the first time, the required parameters are: *\@database_name*, *\@credential_name*, *\@encryption_algorithm*,  *\@enable_backup* The *\@storage_url* parameter is optional.</span></span> <span data-ttu-id="6792c-161">Si no proporciona un valor para el @storage_url parámetro, el valor se deriva utilizando la información de la cuenta de almacenamiento de la credencial de SQL.</span><span class="sxs-lookup"><span data-stu-id="6792c-161">If you do not provide a value for  the @storage_url parameter, the value is derived using the storage account information from the SQL Credential.</span></span> <span data-ttu-id="6792c-162">Si proporciona la dirección URL de almacenamiento, debe proporcionar solo la dirección URL de la raíz de la cuenta de almacenamiento y debe coincidir con la información de la credencial SQL que especificó.</span><span class="sxs-lookup"><span data-stu-id="6792c-162">If you provide the storage URL you should only provide the URL for the root of the storage account, and must match the information in the SQL Credential you specified.</span></span>  
  
    1.  <span data-ttu-id="6792c-163">Conéctese con el [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6792c-163">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
    2.  <span data-ttu-id="6792c-164">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6792c-164">From the Standard bar, click **New Query**.</span></span>  
  
    3.  <span data-ttu-id="6792c-165">Copie y pegue el ejemplo siguiente en la ventana de consulta y haga clic en `Execute` .</span><span class="sxs-lookup"><span data-stu-id="6792c-165">Copy and paste the following example into the query window and click `Execute`.</span></span> <span data-ttu-id="6792c-166">Este ejemplo habilita [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para la base de datos ' TestDB '.</span><span class="sxs-lookup"><span data-stu-id="6792c-166">This example enables [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for the database 'TestDB'.</span></span> <span data-ttu-id="6792c-167">El período de retención se establece en 30 días.</span><span class="sxs-lookup"><span data-stu-id="6792c-167">The retention period is set to 30 days.</span></span> <span data-ttu-id="6792c-168">Este ejemplo utiliza la opción de cifrado especificando el algoritmo de cifrado y la información del sistema de cifrado.</span><span class="sxs-lookup"><span data-stu-id="6792c-168">This sample uses the encryption option by specifying the encryption algorithm and the encryptor information.</span></span>  
  
    ```sql
    Use msdb;  
    GO  
    EXEC smart_admin.sp_set_db_backup   
                    @database_name='TestDB'   
                    ,@enable_backup=1  
                    ,@retention_days =30   
                    ,@credential_name ='MyCredential'  
                    ,@encryption_algorithm ='AES_256'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert'  
    GO
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="6792c-169">El periodo de retención se puede establecer en cualquier valor entre 1 y 30 días.</span><span class="sxs-lookup"><span data-stu-id="6792c-169">The retention period can be set to any value from 1 to 30 days.</span></span>  
    >   
    >  <span data-ttu-id="6792c-170">Para obtener más información sobre cómo crear un certificado para cifrado, vea el paso Crear un certificado de copia de seguridad en [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="6792c-170">For more information on creating a certificate for encryption, see the Create a Backup Certificate step in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span></span>  
  
     <span data-ttu-id="6792c-171">Para obtener más información acerca de este procedimiento almacenado, vea [smart_admin. set_db_backup &#40;Transact-SQL&#41;](https://msdn.microsoft.com/library/dn451013(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="6792c-171">For more information on this stored procedure, see [smart_admin.set_db_backup &#40;Transact-SQL&#41;](https://msdn.microsoft.com/library/dn451013(v=sql.120).aspx)</span></span>  
  
     <span data-ttu-id="6792c-172">Para revisar la configuración de una base de datos, utilice la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="6792c-172">To review the configuration settings for a database use the following query:</span></span>  
  
    ```sql
    Use msdb  
    GO  
    SELECT * FROM smart_admin.fn_backup_db_config('TestDB')  
    ```  
  
##  <a name="enable-and-configure-default-ss_smartbackup-settings-for-the-instance"></a><a name="InstanceConfigure"></a><span data-ttu-id="6792c-173">Habilitar y configurar los valores predeterminados [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para la instancia</span><span class="sxs-lookup"><span data-stu-id="6792c-173">Enable and Configure Default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings for the Instance</span></span>  
 <span data-ttu-id="6792c-174">Puede habilitar y configurar los valores predeterminados en [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] el nivel de instancia de dos maneras: mediante el procedimiento almacenado del sistema `smart_admin.set_instance_backup` o **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="6792c-174">You can enable and configure default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings at the instance level in two ways:  By using the system stored procedure `smart_admin.set_instance_backup` or **SQL Server Management Studio**.</span></span> <span data-ttu-id="6792c-175">Los dos métodos se explica a continuación:</span><span class="sxs-lookup"><span data-stu-id="6792c-175">The two methods are explained below:</span></span>  
  
 <span data-ttu-id="6792c-176">**smart_admin. set_instance_backup:**.</span><span class="sxs-lookup"><span data-stu-id="6792c-176">**smart_admin.set_instance_backup:**.</span></span> <span data-ttu-id="6792c-177">Al especificar el valor **1** para \* \@ enable_backup\* parámetro, puede habilitar la copia de seguridad y establecer las configuraciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="6792c-177">By specifying the value **1** for *\@enable_backup* parameter, you can enable backup and set the default configurations.</span></span> <span data-ttu-id="6792c-178">Una vez aplicadas en el nivel de instancia, estas configuraciones predeterminadas se aplican a todas las bases de datos nuevas que se agregan a esta instancia.</span><span class="sxs-lookup"><span data-stu-id="6792c-178">Once applied at the instance level, these default settings are applied to any new database that is added to this instance.</span></span>  <span data-ttu-id="6792c-179">Cuando [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] se habilita por primera vez, la siguiente información se debe proporcionar además de habilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] en la instancia:</span><span class="sxs-lookup"><span data-stu-id="6792c-179">When [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the first time, the following information must be provided in addition to enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on the instance:</span></span>  
  
-   <span data-ttu-id="6792c-180">El período de retención.</span><span class="sxs-lookup"><span data-stu-id="6792c-180">The retention period.</span></span>  
  
-   <span data-ttu-id="6792c-181">Credencial SQL usada para autenticarse en la cuenta de almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="6792c-181">SQL Credential used to authenticate to the Azure storage account.</span></span>  
  
-   <span data-ttu-id="6792c-182">La opción de cifrado.</span><span class="sxs-lookup"><span data-stu-id="6792c-182">The encryption option.</span></span> <span data-ttu-id="6792c-183">Especifique que no se cifre mediante \* \@ encryption_algorithm\*  =  **NO_ENCRYPTION** o especifique un algoritmo de cifrado admitido.</span><span class="sxs-lookup"><span data-stu-id="6792c-183">Either specify not to encrypt using *\@encryption_algorithm* = **NO_ENCRYPTION** or specify a supported encryption algorithm.</span></span> <span data-ttu-id="6792c-184">Para obtener más información sobre cifrado, vea [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="6792c-184">For more information on encryption, see [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span></span>  
  
 <span data-ttu-id="6792c-185">Una vez que están habilitadas estas opciones, se conservan.</span><span class="sxs-lookup"><span data-stu-id="6792c-185">Once enabled these settings are persisted.</span></span> <span data-ttu-id="6792c-186">Si va a cambiar la configuración, solo se requiere el nombre de la base de datos y el valor que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="6792c-186">If you are changing the configuration, only the database name and the setting you want to change is required.</span></span> [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="6792c-187">conserva los valores existentes cuando no se especifica.</span><span class="sxs-lookup"><span data-stu-id="6792c-187">retains the existing values when not specified.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6792c-188">Antes de configurar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] en una instancia, puede ser útil comprobar la configuración existente.</span><span class="sxs-lookup"><span data-stu-id="6792c-188">Before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on an instance, it might be useful to check for existing configuration, if any.</span></span> <span data-ttu-id="6792c-189">El paso para revisar la configuración de una base de datos se describe más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="6792c-189">The step to reviewing configuration settings for a database is explained later in this section.</span></span>  
  
 <span data-ttu-id="6792c-190">**SQL Server Management Studio**: para realizar esta tarea en SQL Server Management Studio, vaya el Explorador de objetos, expanda el nodo **Administración** y haga clic con el botón derecho en **Copia de seguridad administrada**.</span><span class="sxs-lookup"><span data-stu-id="6792c-190">**SQL Server Management Studio:** To do this task in SQL Server Management Studio, go the object explorer, expand the **Management** node, and right click on **Managed Backup**.</span></span> <span data-ttu-id="6792c-191">Seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="6792c-191">Select **Configure**.</span></span> <span data-ttu-id="6792c-192">Esto abre el cuadro de diálogo **Copia de seguridad administrada**.</span><span class="sxs-lookup"><span data-stu-id="6792c-192">This opens the **Managed Backup** dialog.</span></span> <span data-ttu-id="6792c-193">Use este cuadro de diálogo para especificar el período de retención, la credencial de SQL, la dirección URL de almacenamiento y la configuración de cifrado.</span><span class="sxs-lookup"><span data-stu-id="6792c-193">Use this dialog to specify the retention period, SQL Credential, Storage URL, and the encryption settings.</span></span> <span data-ttu-id="6792c-194">Para obtener ayuda específica sobre este cuadro de diálogo, vea [configurar la &#40;de copia de seguridad administrada SQL Server Management Studio&#41;](configure-managed-backup-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="6792c-194">For specific help with this dialog, see [Configure Managed Backup &#40;SQL Server Management Studio&#41;](configure-managed-backup-sql-server-management-studio.md).</span></span>  
  
#### <a name="using-transact-sql"></a><span data-ttu-id="6792c-195">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6792c-195">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="6792c-196">Conéctese con el [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6792c-196">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6792c-197">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6792c-197">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6792c-198">Copie y pegue el ejemplo siguiente en la ventana de consulta y haga clic en `Execute` .</span><span class="sxs-lookup"><span data-stu-id="6792c-198">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
   EXEC smart_admin.sp_set_instance_backup  
                @retention_days=30   
                ,@credential_name='sqlbackuptoURL'  
                ,@encryption_algorithm ='AES_128'  
                ,@encryptor_type= 'Certificate'  
                ,@encryptor_name='MyBackupCert'  
                ,@enable_backup=1;  
GO  
  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6792c-199">El periodo de retención se puede establecer en cualquier valor entre 1 y 30 días.</span><span class="sxs-lookup"><span data-stu-id="6792c-199">The retention period can be set to any value from 1 to 30 days.</span></span>  
>   
>  <span data-ttu-id="6792c-200">Para obtener más información sobre cómo crear un certificado para cifrado, vea el paso Crear un certificado de copia de seguridad en [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="6792c-200">For more information on creating a certificate for encryption, see the Create a Backup Certificate step in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span></span>  
  
 <span data-ttu-id="6792c-201">Para ver la configuración predeterminada de la instancia, utilice la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="6792c-201">To view the default configuration settings for the instance, use the following query:</span></span>  
  
```sql
Use msdb;  
GO  
SELECT * FROM smart_admin.fn_backup_instance_config ();
```  
  
#### <a name="using-powershell"></a><span data-ttu-id="6792c-202">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="6792c-202">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="6792c-203">Iniciar una instancia de PowerShell</span><span class="sxs-lookup"><span data-stu-id="6792c-203">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="6792c-204">Ejecutar el script siguiente después de modificarlo para adecuarlo a sus valores</span><span class="sxs-lookup"><span data-stu-id="6792c-204">Run the following script after modifying it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    $encryptionOption = New-SqlBackupEncryptionOption -EncryptionAlgorithm Aes128 -EncryptorType ServerCertificate -EncryptorName "MyBackupCert"  
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -BackupEnabled $True -BackupRetentionPeriodInDays 10 -EncryptionOption $encryptionOption  
    ```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6792c-205">Cuando crea una nueva base de datos después de configurar la configuración predeterminada, puede llevar hasta 15 minutos el que la base de datos se configure con las opciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="6792c-205">When you create a new database after configuring the default settings, it may take up to 15 minutes for the database to be configured with the default settings.</span></span> <span data-ttu-id="6792c-206">Esto también se aplica a las bases de datos que se cambian de **Simple** a **Full** o al modo de recuperación **Bulk-Logged** .</span><span class="sxs-lookup"><span data-stu-id="6792c-206">This also applies to databases that are changed from **Simple** to **Full** or **Bulk-Logged** recovery model.</span></span>  
  
##  <a name="disable-ss_smartbackup-for-a-database"></a><a name="DatabaseDisable"></a> <span data-ttu-id="6792c-207">Deshabilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para una base de datos</span><span class="sxs-lookup"><span data-stu-id="6792c-207">Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a database</span></span>  
 <span data-ttu-id="6792c-208">Puede deshabilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] la configuración mediante el `sp_set_db_backup` procedimiento almacenado del sistema.</span><span class="sxs-lookup"><span data-stu-id="6792c-208">You can disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings by using the `sp_set_db_backup` system stored procedure.</span></span> <span data-ttu-id="6792c-209">\* \@ Enableparameter\* se usa para habilitar y deshabilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] las configuraciones de una base de datos específica, donde 1 habilita y 0 deshabilita los valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="6792c-209">The *\@enableparameter* is used to enable and disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configurations for a specific database, where 1 enables and 0 disables the configuration settings.</span></span>  
  
#### <a name="to-disable-ss_smartbackup-for-a-specific-database"></a><span data-ttu-id="6792c-210">Para deshabilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para una base de datos específica:</span><span class="sxs-lookup"><span data-stu-id="6792c-210">To Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a specific database:</span></span>  
  
1.  <span data-ttu-id="6792c-211">Conéctese con el [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6792c-211">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6792c-212">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6792c-212">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6792c-213">Copie y pegue el ejemplo siguiente en la ventana de consulta y haga clic en `Execute` .</span><span class="sxs-lookup"><span data-stu-id="6792c-213">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
EXEC smart_admin.sp_set_db_backup   
                @database_name='TestDB'   
                ,@enable_backup=0;  
GO
```  
  
##  <a name="disable-ss_smartbackup-for-all-the-databases-on-the-instance"></a><a name="DatabaseAllDisable"></a> <span data-ttu-id="6792c-214">Deshabilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para todas las bases de datos de la instancia</span><span class="sxs-lookup"><span data-stu-id="6792c-214">Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for all the databases on the Instance</span></span>  
 <span data-ttu-id="6792c-215">El siguiente procedimiento es válido cuando se desea deshabilitar la configuración de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] de todas las bases de datos que tienen habilitado [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] en la instancia.</span><span class="sxs-lookup"><span data-stu-id="6792c-215">The following procedure is for when you want to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configuration settings from all the databases that currently have [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled on the instance.</span></span>  <span data-ttu-id="6792c-216">Las opciones de configuración como la dirección URL de almacenamiento, la retención y la credencial de SQL permanecerán en los metadatos y se pueden utilizar si [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] se habilita posteriormente para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6792c-216">The configuration settings like the storage URL, retention, and the SQL Credential will remain in the metadata and can be used  if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the database at a later time.</span></span> <span data-ttu-id="6792c-217">Si solo desea pausar los servicios de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] temporalmente, puede usar el modificador principal explicado en las siguientes secciones más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="6792c-217">If you want to just pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services temporarily, you can use the master switch explained in the following sections later in this topic.</span></span>  
  
#### <a name="to-disable-ss_smartbackupfor-all-the-databases"></a><span data-ttu-id="6792c-218">Para deshabilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]para todas las bases de datos:</span><span class="sxs-lookup"><span data-stu-id="6792c-218">To disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]for all the databases:</span></span>  
  
1.  <span data-ttu-id="6792c-219">Conéctese con el [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6792c-219">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6792c-220">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6792c-220">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6792c-221">Copie y pegue el ejemplo siguiente en la ventana de consulta y haga clic en `Execute` .</span><span class="sxs-lookup"><span data-stu-id="6792c-221">Copy and paste the following example into the query window and click `Execute`.</span></span> <span data-ttu-id="6792c-222">El ejemplo siguiente identifica si [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] se configura en el nivel de instancia y todas las bases de datos habilitadas para [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] en la instancia y ejecuta el procedimiento almacenado del sistema `sp_set_db_backup` para deshabilitar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6792c-222">The following example identifies if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is configured at the instance level and all the [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled databases on the instance, and executes the system stored procedure `sp_set_db_backup` to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span>  
  
```sql
-- Create a working table to store the database names  
Declare @DBNames TABLE  
  
       (  
             RowID int IDENTITY PRIMARY KEY  
             ,DBName varchar(500)  
  
       )  
-- Define the variables  
DECLARE @rowid int  
DECLARE @dbname varchar(500)  
DECLARE @SQL varchar(2000)  
-- Get the database names from the system function  
  
INSERT INTO @DBNames (DBName)  
  
SELECT db_name  
       FROM
  
       smart_admin.fn_backup_db_config (NULL)  
       WHERE is_smart_backup_enabled = 1  
  
       --Select DBName from @DBNames 
       select @rowid = min(RowID) FROM @DBNames  
  
       WHILE @rowID IS NOT NULL  
       Begin
             Set @dbname = (Select DBName From @DBNames Where RowID = @rowid)  
             Begin  
             Set @SQL = 'EXEC smart_admin.sp_set_db_backup    
                @database_name= '''+'' + @dbname+ ''+''',   
                @enable_backup=0'  
  
            EXECUTE (@SQL)  
  
             END  
             Select @rowid = min(RowID)  
             From @DBNames Where RowID > @rowid  
  
       END
```  
  
 <span data-ttu-id="6792c-223">Para revisar la configuración predeterminada de todas las bases de datos en la instancia, utilice la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="6792c-223">To review the configuration settings for all the databases on the instance, use the following query:</span></span>  
  
```sql
Use msdb;  
GO  
SELECT * FROM smart_admin.fn_backup_db_config (NULL);  
GO
```  
  
##  <a name="disable-default-ss_smartbackup-settings-for-the-instance"></a><a name="InstanceDisable"></a> <span data-ttu-id="6792c-224">Deshabilitar la configuración predeterminada de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] de la instancia</span><span class="sxs-lookup"><span data-stu-id="6792c-224">Disable Default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings for the Instance</span></span>  
 <span data-ttu-id="6792c-225">La configuración predeterminada en el nivel de instancia se aplica a todas las nuevas bases de datos creadas en esa instancia.</span><span class="sxs-lookup"><span data-stu-id="6792c-225">Default settings at the instance level apply to all new databases created on that instance.</span></span>  <span data-ttu-id="6792c-226">Si ya no requiere configuración predeterminada, puede deshabilitarla mediante el procedimiento almacenado del sistema **smart_admin.sp_set_instance_backup** .</span><span class="sxs-lookup"><span data-stu-id="6792c-226">If you no longer need or require default settings, you can disable this configuration by using the **smart_admin.sp_set_instance_backup** System stored procedure.</span></span> <span data-ttu-id="6792c-227">Al deshabilitarla, no se quita las otras opciones de configuración como la dirección URL de almacenamiento, el valor de retención o el nombre de la credencial de SQL.</span><span class="sxs-lookup"><span data-stu-id="6792c-227">Disabling does not remove the other configuration settings like the storage URL, retention setting, or the SQL Credential name.</span></span> <span data-ttu-id="6792c-228">Estas opciones se utilizarán si [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] se habilita para la instancia posteriormente.</span><span class="sxs-lookup"><span data-stu-id="6792c-228">These settings will be used if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the instance at a later time.</span></span>  
  
#### <a name="to-disable-ss_smartbackup-default-configuration-settings"></a><span data-ttu-id="6792c-229">Para deshabilitar la configuración predeterminada de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="6792c-229">To disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] default configuration settings:</span></span>  
  
1.  <span data-ttu-id="6792c-230">Conéctese con el [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6792c-230">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6792c-231">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6792c-231">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6792c-232">Copie y pegue el ejemplo siguiente en la ventana de consulta y haga clic en `Execute` .</span><span class="sxs-lookup"><span data-stu-id="6792c-232">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
    ```sql
    Use msdb;  
    Go  
    EXEC smart_admin.sp_set_instance_backup  
                    @enable_backup=0;  
    GO
    ```  
  
#### <a name="using-powershell"></a><span data-ttu-id="6792c-233">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="6792c-233">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="6792c-234">Iniciar una instancia de PowerShell</span><span class="sxs-lookup"><span data-stu-id="6792c-234">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="6792c-235">Ejecute el siguiente script:</span><span class="sxs-lookup"><span data-stu-id="6792c-235">Run the following script:</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Set-SqlSmartAdmin -BackupEnabled $False  
    ```  
  
##  <a name="pause-ss_smartbackup-at-the-instance-level"></a><a name="InstancePause"></a> <span data-ttu-id="6792c-236">Pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] en el nivel de instancia</span><span class="sxs-lookup"><span data-stu-id="6792c-236">Pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Instance Level</span></span>  
 <span data-ttu-id="6792c-237">Puede haber ocasiones en que deba detener temporalmente los servicios de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] durante un breve período.</span><span class="sxs-lookup"><span data-stu-id="6792c-237">There might be times when you need to temporarily pause the [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services for a short period time.</span></span>  <span data-ttu-id="6792c-238">El procedimiento almacenado del sistema `smart_admin.sp_backup_master_switch` permite deshabilitar el servicio de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] en el nivel de instancia.</span><span class="sxs-lookup"><span data-stu-id="6792c-238">The `smart_admin.sp_backup_master_switch` system stored procedure allows you to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] service at the instance level.</span></span>  <span data-ttu-id="6792c-239">El mismo procedimiento almacenado se utiliza para reanudar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6792c-239">The same stored procedure is used to resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="6792c-240">El parámetro @state se utiliza para definir si [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] debe desactivarse o activarse.</span><span class="sxs-lookup"><span data-stu-id="6792c-240">The @state parameter is used to define whether [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] should be turned off or on.</span></span>  
  
#### <a name="to-pause-ss_smartbackup-services-using-transact-sql"></a><span data-ttu-id="6792c-241">Para pausar los servicios de [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] con Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="6792c-241">To Pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Services Using Transact-SQL:</span></span>  
  
1.  <span data-ttu-id="6792c-242">Conéctese con el [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6792c-242">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6792c-243">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6792c-243">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6792c-244">Copie y pegue el ejemplo siguiente en la ventana de consulta y, a continuación, haga clic en`Execute`</span><span class="sxs-lookup"><span data-stu-id="6792c-244">Copy and paste the following example into the query window and then click `Execute`</span></span>  
  
```sql
Use msdb;  
GO  
EXEC smart_admin.sp_backup_master_switch @new_state=0;  
Go  
  
```  
  
#### <a name="to-pause-ss_smartbackup-using-powershell"></a><span data-ttu-id="6792c-245">Para pausar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="6792c-245">To pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using PowerShell</span></span>  
  
1.  <span data-ttu-id="6792c-246">Iniciar una instancia de PowerShell</span><span class="sxs-lookup"><span data-stu-id="6792c-246">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="6792c-247">Ejecutar el script siguiente después de modificarlo para adecuarlo a sus valores</span><span class="sxs-lookup"><span data-stu-id="6792c-247">Run the following script after you modify it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -MasterSwitch $False  
    ```  
  
#### <a name="to-resume-ss_smartbackup-using-transact-sql"></a><span data-ttu-id="6792c-248">Para reanudar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6792c-248">To resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="6792c-249">Conéctese con el [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6792c-249">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6792c-250">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6792c-250">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6792c-251">Copie y pegue el ejemplo siguiente en la ventana de consulta y, a continuación, haga clic en `Execute` .</span><span class="sxs-lookup"><span data-stu-id="6792c-251">Copy and paste the following example into the query window and then click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
EXEC smart_admin. sp_backup_master_switch @new_state=1;  
GO
```  
  
#### <a name="to-resume-ss_smartbackup-using-powershell"></a><span data-ttu-id="6792c-252">Para reanudar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="6792c-252">To resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using PowerShell</span></span>  
  
1.  <span data-ttu-id="6792c-253">Iniciar una instancia de PowerShell</span><span class="sxs-lookup"><span data-stu-id="6792c-253">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="6792c-254">Ejecutar el script siguiente después de modificarlo para adecuarlo a sus valores</span><span class="sxs-lookup"><span data-stu-id="6792c-254">Run the following script after you modify it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -MasterSwitch $True  
    ```  
