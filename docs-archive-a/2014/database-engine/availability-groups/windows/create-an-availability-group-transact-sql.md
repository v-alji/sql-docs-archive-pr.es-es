---
title: Crear un grupo de disponibilidad (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], creating
ms.assetid: 8b0a6301-8b79-4415-b608-b40876f30066
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57a494af168a8f5572bafe93f8fb47b22a954a19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752350"
---
# <a name="create-an-availability-group-transact-sql"></a><span data-ttu-id="b47e6-102">Crear un grupo de disponibilidad (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b47e6-102">Create an Availability Group (Transact-SQL)</span></span>
  <span data-ttu-id="b47e6-103">En este tema se describe cómo usar [!INCLUDE[tsql](../../../includes/tsql-md.md)] para crear y configurar un grupo de disponibilidad en las instancias de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] en que se habilita la característica de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b47e6-103">This topic describes how to use [!INCLUDE[tsql](../../../includes/tsql-md.md)] to create and configure an availability group on instances of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] on which the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature is enabled.</span></span> <span data-ttu-id="b47e6-104">Un *grupo de disponibilidad* define un conjunto de bases de datos de usuario que realizarán la conmutación por error como una sola unidad y un conjunto de asociados de conmutación por error, conocido como *réplicas de disponibilidad*, que admiten la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="b47e6-104">An *availability group* defines a set of user databases that will fail over as a single unit and a set of failover partners, known as *availability replicas*, that support failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b47e6-105">Para obtener una introducción a los grupos de disponibilidad, vea [Información general de los grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b47e6-105">For an introduction to availability groups, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  

> [!NOTE]  
>  <span data-ttu-id="b47e6-106">Como alternativa al uso de [!INCLUDE[tsql](../../../includes/tsql-md.md)], puede usar el Asistente para crear grupo de disponibilidad o cmdlets de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b47e6-106">As an alternative to using [!INCLUDE[tsql](../../../includes/tsql-md.md)], you can use the Create Availability Group wizard or [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell cmdlets.</span></span> <span data-ttu-id="b47e6-107">Para obtener más información, vea [Usar el Asistente para grupo de disponibilidad &#40;SQL Server Management Studio&#41;](use-the-availability-group-wizard-sql-server-management-studio.md), [Usar el cuadro de diálogo Nuevo grupo de disponibilidad &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)o [Crear un grupo de disponibilidad &#40;SQL Server PowerShell&#41;](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b47e6-107">For more information, see [Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-availability-group-wizard-sql-server-management-studio.md), [Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md), or [Create an Availability Group &#40;SQL Server PowerShell&#41;](../../../powershell/sql-server-powershell.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b47e6-108">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="b47e6-108">Before You Begin</span></span>  
 <span data-ttu-id="b47e6-109">Se recomienda encarecidamente leer esta sección antes de intentar crear el primer grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b47e6-109">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
###  <a name="prerequisites-restrictions-and-recommendations"></a><a name="PrerequisitesRestrictions"></a><span data-ttu-id="b47e6-110">Requisitos previos, restricciones y recomendaciones</span><span class="sxs-lookup"><span data-stu-id="b47e6-110">Prerequisites, Restrictions, and Recommendations</span></span>  
  
-   <span data-ttu-id="b47e6-111">Antes de crear un grupo de disponibilidad, compruebe que las instancias de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospedan réplicas de disponibilidad residen en otro nodo (WSFC) de clúster de conmutación por error de Windows Server en el mismo clúster de conmutación por error de WSFC.</span><span class="sxs-lookup"><span data-stu-id="b47e6-111">Before creating an availability group, verify that the instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that host availability replicas reside on different Windows Server Failover Clustering (WSFC) node within the same WSFC failover cluster.</span></span> <span data-ttu-id="b47e6-112">Además, compruebe que cada una de las instancias del servidor cumple los requisitos previos de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b47e6-112">Also, verify that each of the server instance meets all other [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] prerequisites.</span></span> <span data-ttu-id="b47e6-113">Para más información, recomendamos encarecidamente que lea [Requisitos previos, restricciones y recomendaciones para grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="b47e6-113">For more information, we strongly recommend that you read [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b47e6-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b47e6-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b47e6-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="b47e6-115">Permissions</span></span>  
 <span data-ttu-id="b47e6-116">Se requiere la pertenencia al rol fijo de servidor **sysadmin** y el permiso de servidor CREATE AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="b47e6-116">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
###  <a name="summary-of-tasks-and-corresponding-transact-sql-statements"></a><a name="SummaryTsqlStatements"></a> <span data-ttu-id="b47e6-117">Resumen de las tareas e instrucciones Transact-SQL correspondientes</span><span class="sxs-lookup"><span data-stu-id="b47e6-117">Summary of Tasks and Corresponding Transact-SQL Statements</span></span>  
 <span data-ttu-id="b47e6-118">En la tabla siguiente se enumeran las tareas básicas relacionadas con la creación y configuración de un grupo de disponibilidad y se indican las instrucciones [!INCLUDE[tsql](../../../includes/tsql-md.md)] que han de utilizarse para estas tareas.</span><span class="sxs-lookup"><span data-stu-id="b47e6-118">The following table lists the basic tasks involved in creating and configuring an availability group and indicates which [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements to use for these tasks.</span></span> <span data-ttu-id="b47e6-119">Las tareas de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] se deben realizar en la secuencia en que se muestran en la tabla.</span><span class="sxs-lookup"><span data-stu-id="b47e6-119">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] tasks must be performed in the sequence in which they are presented in the table.</span></span>  
  
|<span data-ttu-id="b47e6-120">Tarea</span><span class="sxs-lookup"><span data-stu-id="b47e6-120">Task</span></span>|<span data-ttu-id="b47e6-121">Instrucciones Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b47e6-121">Transact-SQL Statement(s)</span></span>|<span data-ttu-id="b47e6-122">Dónde realizar la tarea**<sup>\*</sup>**</span><span class="sxs-lookup"><span data-stu-id="b47e6-122">Where to Perform Task**<sup>\*</sup>**</span></span>|  
|----------|----------------------------------|-------------------------------------------|  
|<span data-ttu-id="b47e6-123">Crear extremo de creación de reflejo de la base de datos (una vez por instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="b47e6-123">Create database mirroring endpoint (once per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance)</span></span>|<span data-ttu-id="b47e6-124">[Crear punto de conexión](/sql/t-sql/statements/create-endpoint-transact-sql) *endpointName* ... POR DATABASE_MIRRORING</span><span class="sxs-lookup"><span data-stu-id="b47e6-124">[CREATE ENDPOINT](/sql/t-sql/statements/create-endpoint-transact-sql) *endpointName* ... FOR DATABASE_MIRRORING</span></span>|<span data-ttu-id="b47e6-125">Se ejecuta en cada instancia del servidor que carece de extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b47e6-125">Execute on each server instance that lacks database mirroring endpoint.</span></span>|  
|<span data-ttu-id="b47e6-126">Crear grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="b47e6-126">Create availability group</span></span>|[<span data-ttu-id="b47e6-127">CREATE AVAILABILITY GROUP</span><span class="sxs-lookup"><span data-stu-id="b47e6-127">CREATE AVAILABILITY GROUP</span></span>](/sql/t-sql/statements/create-availability-group-transact-sql)|<span data-ttu-id="b47e6-128">Se ejecuta en la instancia del servidor que va a hospedar la réplica principal inicial.</span><span class="sxs-lookup"><span data-stu-id="b47e6-128">Execute on the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="b47e6-129">Unir la réplica secundaria al grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="b47e6-129">Join secondary replica to availability group</span></span>|<span data-ttu-id="b47e6-130">[ALTER AVAILABILITY GROUP](join-a-secondary-replica-to-an-availability-group-sql-server.md) *group_name* JOIN</span><span class="sxs-lookup"><span data-stu-id="b47e6-130">[ALTER AVAILABILITY GROUP](join-a-secondary-replica-to-an-availability-group-sql-server.md) *group_name* JOIN</span></span>|<span data-ttu-id="b47e6-131">Se ejecuta en cada una de las instancias del servidor que hospedan una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="b47e6-131">Execute on each server instance that hosts a secondary replica.</span></span>|  
|<span data-ttu-id="b47e6-132">Preparar la base de datos secundaria</span><span class="sxs-lookup"><span data-stu-id="b47e6-132">Prepare the secondary database</span></span>|<span data-ttu-id="b47e6-133">[Copias de seguridad](/sql/t-sql/statements/backup-transact-sql) y [restauración](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b47e6-133">[BACKUP](/sql/t-sql/statements/backup-transact-sql) and [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>|<span data-ttu-id="b47e6-134">Se crean las copias de seguridad de la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="b47e6-134">Create backups on the server instance that hosts the primary replica.</span></span><br /><br /> <span data-ttu-id="b47e6-135">Se restauran las copias de seguridad en cada una de las instancias del servidor que hospedan una réplica secundaria utilizando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="b47e6-135">Restore backups on each server instance that hosts a secondary replica, using RESTORE WITH NORECOVERY.</span></span>|  
|<span data-ttu-id="b47e6-136">Iniciar la sincronización de datos uniendo cada base de datos secundaria al grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="b47e6-136">Start data synchronization by joining each secondary database to availability group</span></span>|<span data-ttu-id="b47e6-137">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span><span class="sxs-lookup"><span data-stu-id="b47e6-137">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span></span>|<span data-ttu-id="b47e6-138">Se ejecuta en cada una de las instancias del servidor que hospedan una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="b47e6-138">Execute on each server instance that hosts a secondary replica.</span></span>|  
  
 <span data-ttu-id="b47e6-139">**<sup>\*</sup>** Para realizar una tarea determinada, conéctese a la instancia o instancias del servidor indicadas.</span><span class="sxs-lookup"><span data-stu-id="b47e6-139">**<sup>\*</sup>**  To perform a given task, connect to the indicated server instance or instances.</span></span>  
  
##  <a name="using-transact-sql-to-create-and-configure-an-availability-group"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b47e6-140">Usar Transact-SQL para crear y configurar un grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="b47e6-140">Using Transact-SQL to Create and Configure an Availability Group</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b47e6-141"> Para consultar un procedimiento de configuración de ejemplo que contiene ejemplos de código de cada una de estas instrucciones [!INCLUDE[tsql](../../../includes/tsql-md.md)] , vea [Ejemplo: configurar un grupo de disponibilidad que utilice la Autenticación de Windows](#ExampleConfigAGWinAuth).</span><span class="sxs-lookup"><span data-stu-id="b47e6-141">For a sample configuration procedure containing code examples of each these [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements, see [Example: Configuring an Availability Group that Uses Windows Authentication](#ExampleConfigAGWinAuth).</span></span>  
  
1.  <span data-ttu-id="b47e6-142">Conéctese a la instancia del servidor que va a hospedar la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="b47e6-142">Connect to the server instance that is to host the primary replica.</span></span>  
  
2.  <span data-ttu-id="b47e6-143">Cree el grupo de disponibilidad mediante la instrucción [Create Availability Group](/sql/t-sql/statements/create-availability-group-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b47e6-143">Create the availability group by using the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
3.  <span data-ttu-id="b47e6-144">Una la nueva réplica secundaria al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b47e6-144">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="b47e6-145">Para obtener más información, vea [Combinar una réplica secundaria con un grupo de disponibilidad &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b47e6-145">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="b47e6-146">Para cada base de datos del grupo de disponibilidad, cree una base de datos secundaria restaurando las copias de seguridad recientes de la base de datos principal, utilizando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="b47e6-146">For each database in the availability group, create a secondary database by restoring recent backups of the primary database, using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="b47e6-147">Para obtener más información, vea [Ejemplo: configurar un grupo de disponibilidad que use la Autenticación de Windows (Transact-SQL)](create-an-availability-group-transact-sql.md), comenzando por el paso que restaura la copia de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b47e6-147">For more information, see [Example: Setting Up an Availability Group Using Windows Authentication (Transact-SQL)](create-an-availability-group-transact-sql.md), starting with the step that restores the database backup.</span></span>  
  
5.  <span data-ttu-id="b47e6-148">Una cada nueva base de datos secundaria al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b47e6-148">Join every new secondary database to the availability group.</span></span> <span data-ttu-id="b47e6-149">Para obtener más información, vea [Combinar una réplica secundaria con un grupo de disponibilidad &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b47e6-149">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
##  <a name="example-configuring-an-availability-group-that-uses-windows-authentication"></a><a name="ExampleConfigAGWinAuth"></a> <span data-ttu-id="b47e6-150">Ejemplo: configurar un grupo de disponibilidad que use la Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="b47e6-150">Example: Configuring an Availability Group that Uses Windows Authentication</span></span>  
 <span data-ttu-id="b47e6-151">En este ejemplo se crea un procedimiento de configuración de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] de ejemplo que utiliza [!INCLUDE[tsql](../../../includes/tsql-md.md)] para configurar los extremos de creación de reflejo de la base de datos que utilizan la Autenticación de Windows y para crear y configurar un grupo de disponibilidad y sus bases de datos secundarias.</span><span class="sxs-lookup"><span data-stu-id="b47e6-151">This example creates a sample [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] configuration procedure that uses [!INCLUDE[tsql](../../../includes/tsql-md.md)] to set up database mirroring endpoints that use Windows Authentication and to create and configure an availability group and its secondary databases.</span></span>  
  
 <span data-ttu-id="b47e6-152">Este ejemplo contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="b47e6-152">This example contains the following sections:</span></span>  
  
-   [<span data-ttu-id="b47e6-153">Requisitos previos para usar el procedimiento de configuración de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b47e6-153">Prerequisites for Using the Sample Configuration Procedure</span></span>](#PrerequisitesForExample)  
  
-   [<span data-ttu-id="b47e6-154">Procedimiento de configuración de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b47e6-154">Sample Configuration Procedure</span></span>](#SampleProcedure)  
  
-   [<span data-ttu-id="b47e6-155">Ejemplo completo de código del procedimiento de configuración de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b47e6-155">Complete Code Example for Sample Configuration Procedure</span></span>](#CompleteCodeExample)  
  
###  <a name="prerequisites-for-using-the-sample-configuration-procedure"></a><a name="PrerequisitesForExample"></a> <span data-ttu-id="b47e6-156">Requisitos previos para utilizar el procedimiento de configuración de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b47e6-156">Prerequisites for Using the Sample Configuration Procedure</span></span>  
 <span data-ttu-id="b47e6-157">Este procedimiento de ejemplo tiene los requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b47e6-157">This sample procedure has the following requirements:</span></span>  
  
-   <span data-ttu-id="b47e6-158">Las instancias del servidor deben admitir [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b47e6-158">The server instances must support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="b47e6-159">Para más información, vea [Requisitos previos, restricciones y recomendaciones para grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="b47e6-159">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
-   <span data-ttu-id="b47e6-160">Debe haber dos bases de datos, *MyDb1* y *MyDb2*, en la instancia del servidor que va a hospedar la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="b47e6-160">Two sample databases, *MyDb1* and *MyDb2*, must exist on the server instance that will host the primary replica.</span></span> <span data-ttu-id="b47e6-161">En los siguientes ejemplos de código se crean y configuran estas dos bases de datos y se crea una copia de seguridad completa de cada una.</span><span class="sxs-lookup"><span data-stu-id="b47e6-161">The following code examples create and configure these two databases and create a full backup of each.</span></span> <span data-ttu-id="b47e6-162">Ejecute estos ejemplos de código en la instancia del servidor en que desea crear el grupo de disponibilidad de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b47e6-162">Execute these code examples on the server instance on which you intend to create the sample availability group.</span></span> <span data-ttu-id="b47e6-163">Esta instancia del servidor hospedará la réplica principal inicial del grupo de disponibilidad de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b47e6-163">This server instance will host the initial primary replica of the sample availability group.</span></span>  
  
    1.  <span data-ttu-id="b47e6-164">En el siguiente ejemplo de [!INCLUDE[tsql](../../../includes/tsql-md.md)] se crean estas bases de datos y se modifican para utilizar el modelo de recuperación completa:</span><span class="sxs-lookup"><span data-stu-id="b47e6-164">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] example creates these databases and alters them to use the full recovery model:</span></span>  
  
        ```sql
        -- Create sample databases:  
        CREATE DATABASE MyDb1;  
        GO  
        ALTER DATABASE MyDb1 SET RECOVERY FULL;  
        GO  
  
        CREATE DATABASE MyDb2;  
        GO  
        ALTER DATABASE MyDb2 SET RECOVERY FULL;  
        GO  
        ```  
  
    2.  <span data-ttu-id="b47e6-165">En el ejemplo de código siguiente se crea una copia de seguridad completa de las bases de datos *MyDb1* y *MyDb2*.</span><span class="sxs-lookup"><span data-stu-id="b47e6-165">The following code example creates a full database backup of *MyDb1* and *MyDb2*.</span></span> <span data-ttu-id="b47e6-166">En este ejemplo de código se usa un recurso compartido de copia de seguridad ficticio, \\ \\ *fileserver* \\ *SQLbackups*.</span><span class="sxs-lookup"><span data-stu-id="b47e6-166">This code example uses a fictional backup share, \\\\*FILESERVER*\\*SQLbackups*.</span></span>  
  
        ```sql
        -- Backup sample databases:  
        BACKUP DATABASE MyDb1   
        TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
            WITH FORMAT  
        GO  
  
        BACKUP DATABASE MyDb2   
        TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
            WITH FORMAT  
        GO
        ```  
  
###  <a name="sample-configuration-procedure"></a><a name="SampleProcedure"></a> <span data-ttu-id="b47e6-167">Procedimiento de configuración de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b47e6-167">Sample Configuration Procedure</span></span>  
 <span data-ttu-id="b47e6-168">En esta configuración de ejemplo, la réplica de disponibilidad se creará en dos instancias del servidor independientes cuyas cuentas de servicio se ejecutan en diferentes dominios de confianza (`DOMAIN1` y `DOMAIN2`).</span><span class="sxs-lookup"><span data-stu-id="b47e6-168">In this sample configuration, the availability replica will be created on two stand-alone server instances whose service accounts run under different, but trusted, domains (`DOMAIN1` and `DOMAIN2`).</span></span>  
  
 <span data-ttu-id="b47e6-169">En la siguiente tabla se resumen los valores utilizados en esta configuración de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b47e6-169">The following table summarizes the values used in this sample configuration.</span></span>  
  
|<span data-ttu-id="b47e6-170">Rol inicial</span><span class="sxs-lookup"><span data-stu-id="b47e6-170">Initial role</span></span>|<span data-ttu-id="b47e6-171">Sistema</span><span class="sxs-lookup"><span data-stu-id="b47e6-171">System</span></span>|<span data-ttu-id="b47e6-172">Hospeda la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b47e6-172">Host [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Instance</span></span>|  
|------------------|------------|---------------------------------------------|  
|<span data-ttu-id="b47e6-173">Principal</span><span class="sxs-lookup"><span data-stu-id="b47e6-173">Primary</span></span>|`COMPUTER01`|`AgHostInstance`|  
|<span data-ttu-id="b47e6-174">Secundario</span><span class="sxs-lookup"><span data-stu-id="b47e6-174">Secondary</span></span>|`COMPUTER02`|<span data-ttu-id="b47e6-175">instancia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b47e6-175">Default instance.</span></span>|  
  
1.  <span data-ttu-id="b47e6-176">Cree un punto de conexión de creación de reflejo de la base de datos denominado *dbm_endpoint* en la instancia del servidor en la que planea crear el grupo de disponibilidad (se trata de una instancia llamada `AgHostInstance` en `COMPUTER01`).</span><span class="sxs-lookup"><span data-stu-id="b47e6-176">Create a database mirroring endpoint named *dbm_endpoint* on the server instance on which you plan to create the availability group (this is an instance named `AgHostInstance` on `COMPUTER01`).</span></span> <span data-ttu-id="b47e6-177">Este punto de conexión usa el puerto 7022.</span><span class="sxs-lookup"><span data-stu-id="b47e6-177">This endpoint uses port 7022.</span></span> <span data-ttu-id="b47e6-178">Tenga en cuenta que la instancia del servidor en que se crea el grupo de disponibilidad hospedará la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="b47e6-178">Note that the server instance on which you create the availability group will host the primary replica.</span></span>  
  
    ```sql
    -- Create endpoint on server instance that hosts the primary replica:  
    CREATE ENDPOINT dbm_endpoint  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO
    ```  
  
2.  <span data-ttu-id="b47e6-179">Cree un punto de conexión *dbm_endpoint* en la instancia del servidor que hospedará la réplica secundaria (se trata de la instancia del servidor predeterminada en `COMPUTER02`).</span><span class="sxs-lookup"><span data-stu-id="b47e6-179">Create an endpoint *dbm_endpoint* on the server instance that will host the secondary replica (this is the default server instance on `COMPUTER02`).</span></span> <span data-ttu-id="b47e6-180">Este extremo usa el puerto 5022.</span><span class="sxs-lookup"><span data-stu-id="b47e6-180">This endpoint uses port 5022.</span></span>  
  
    ```sql
    -- Create endpoint on server instance that hosts the secondary replica:   
    CREATE ENDPOINT dbm_endpoint  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=5022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO
    ```  
  
3.  > [!NOTE]  
    >  <span data-ttu-id="b47e6-181">Si las cuentas de servicio de las instancias del servidor que van a hospedar las réplicas de disponibilidad se ejecutan en la misma cuenta de dominio, este paso no es necesario.</span><span class="sxs-lookup"><span data-stu-id="b47e6-181">If the service accounts of the server instances that are to host your availability replicas run under the same domain account this step is unnecessary.</span></span> <span data-ttu-id="b47e6-182">Omítalo y vaya directamente al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="b47e6-182">Skip it and go directly to the next step.</span></span>  
  
     <span data-ttu-id="b47e6-183">Si las cuentas de servicio de las instancias del servidor se ejecutan en usuarios de dominio diferentes, en cada instancia del servidor, cree un inicio de sesión para la otra instancia del servidor y conceda este permiso de inicio de sesión para tener acceso al extremo de creación de reflejo de la base de datos local.</span><span class="sxs-lookup"><span data-stu-id="b47e6-183">If the service accounts of the server instances run under different domain users, on each server instance, create a login for the other server instance and grant this login permission to access the local database mirroring endpoint.</span></span>  
  
     <span data-ttu-id="b47e6-184">En el ejemplo de código siguiente se muestran las instrucciones [!INCLUDE[tsql](../../../includes/tsql-md.md)] para crear un inicio de sesión y concederle permiso en un extremo.</span><span class="sxs-lookup"><span data-stu-id="b47e6-184">The following code example shows the [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements for creating a login and granting it permission on an endpoint.</span></span> <span data-ttu-id="b47e6-185">La cuenta de dominio de la instancia del servidor remoto se representa aquí como *domain_name*\\*user_name*.</span><span class="sxs-lookup"><span data-stu-id="b47e6-185">The domain account of the remote server instance is represented here as *domain_name*\\*user_name*.</span></span>  
  
    ```sql
    -- If necessary, create a login for the service account, domain_name\user_name  
    -- of the server instance that will host the other replica:  
    USE master;  
    GO  
    CREATE LOGIN [domain_name\user_name] FROM WINDOWS;  
    GO  
    -- And Grant this login connect permissions on the endpoint:  
    GRANT CONNECT ON ENDPOINT::dbm_endpoint   
       TO [domain_name\user_name];  
    GO  
    ```  
  
4.  <span data-ttu-id="b47e6-186">En la instancia del servidor donde residen las bases de datos de usuario, cree el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b47e6-186">On the server instance where the user databases reside, create the availability group.</span></span>  
  
     <span data-ttu-id="b47e6-187">En el ejemplo de código siguiente se crea un grupo de disponibilidad denominado *MyAG* en la instancia del servidor en la que se crearon las bases de datos de ejemplo, *MyDb1* y *MyDb2*.</span><span class="sxs-lookup"><span data-stu-id="b47e6-187">The following code example creates an availability group named *MyAG* on the server instance on which the sample databases, *MyDb1* and *MyDb2*, were created.</span></span> <span data-ttu-id="b47e6-188">La instancia del servidor local, `AgHostInstance`, en *COMPUTER01* se especifica primero.</span><span class="sxs-lookup"><span data-stu-id="b47e6-188">The local server instance, `AgHostInstance`, on *COMPUTER01* is specified first.</span></span> <span data-ttu-id="b47e6-189">Esta instancia hospedará la réplica principal inicial.</span><span class="sxs-lookup"><span data-stu-id="b47e6-189">This instance will host the initial primary replica.</span></span> <span data-ttu-id="b47e6-190">Una instancia del servidor remoto, la instancia del servidor predeterminada en *COMPUTER02*, se especifica para hospedar una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="b47e6-190">A remote server instance, the default server instance on *COMPUTER02*, is specified to host a secondary replica.</span></span> <span data-ttu-id="b47e6-191">Ambas réplicas de disponibilidad están configuradas para usar el modo de confirmación asincrónica con conmutación por error manual (para las réplicas de confirmación asincrónica, la conmutación por error manual significa una conmutación por error forzada con posible pérdida de datos).</span><span class="sxs-lookup"><span data-stu-id="b47e6-191">Both availability replica are configured to use asynchronous-commit mode with manual failover (for asynchronous-commit replicas manual failover means  forced failover with possible data loss).</span></span>  
  
    ```sql
    -- Create the availability group, MyAG:   
    CREATE AVAILABILITY GROUP MyAG   
       FOR   
          DATABASE MyDB1, MyDB2   
       REPLICA ON   
          'COMPUTER01\AgHostInstance' WITH   
             (  
             ENDPOINT_URL = 'TCP://COMPUTER01.Adventure-Works.com:7022',   
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             ),  
          'COMPUTER02' WITH   
             (  
             ENDPOINT_URL = 'TCP://COMPUTER02.Adventure-Works.com:5022',  
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             );   
    GO  
    ```  
  
     <span data-ttu-id="b47e6-192">Para obtener ejemplos adicionales de código [!INCLUDE[tsql](../../../includes/tsql-md.md)] para la creación de un grupo de disponibilidad, vea [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b47e6-192">For additional [!INCLUDE[tsql](../../../includes/tsql-md.md)] code examples of creating an availability group, see [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span></span>  
  
5.  <span data-ttu-id="b47e6-193">En la instancia del servidor que hospeda la réplica secundaria, combine la réplica secundaria con el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b47e6-193">On the server instance that hosts the secondary replica, join the secondary replica to the availability group.</span></span>  
  
     <span data-ttu-id="b47e6-194">En el ejemplo de código siguiente se une la réplica secundaria de `COMPUTER02` al grupo de disponibilidad `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="b47e6-194">The following code example joins the secondary replica on `COMPUTER02` to the `MyAG` availability group.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- join the secondary replica to the availability group:  
    ALTER AVAILABILITY GROUP MyAG JOIN;  
    GO  
    ```  
  
6.  <span data-ttu-id="b47e6-195">En la instancia del servidor que hospeda la réplica secundaria, cree las bases de datos secundarias.</span><span class="sxs-lookup"><span data-stu-id="b47e6-195">On the server instance that hosts the secondary replica, create the secondary databases.</span></span>  
  
     <span data-ttu-id="b47e6-196">En el ejemplo de código siguiente se crean las bases de datos secundarias *MyDb1* y *MyDb2* mediante la restauración de las copias de seguridad de base de datos con RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="b47e6-196">The following code example creates the *MyDb1* and *MyDb2* secondary databases by restoring database backups using RESTORE WITH NORECOVERY.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- Restore database backups using the WITH NORECOVERY option:  
    RESTORE DATABASE MyDb1   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH NORECOVERY  
    GO  
  
    RESTORE DATABASE MyDb2   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITH NORECOVERY  
    GO
    ```  
  
7.  <span data-ttu-id="b47e6-197">En la instancia del servidor que hospeda la réplica principal, realice una copia de seguridad del registro de transacciones en cada una de las bases de datos principales.</span><span class="sxs-lookup"><span data-stu-id="b47e6-197">On the server instance that hosts the primary replica, back up the transaction log on each of the primary databases.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b47e6-198">Cuando configure un grupo de disponibilidad real, conviene que, antes de realizar la copia de seguridad de registros, suspenda las tareas de copia de seguridad de registros para las bases de datos principales hasta haber combinado las bases de datos secundarias con el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b47e6-198">When you are configuring a real availability group, we recommend that, before taking this log backup, you suspend log backup tasks for your primary databases until you have joined the corresponding secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="b47e6-199">En el ejemplo de código siguiente se crea una copia de seguridad del registro de transacciones en MyDb1 y en MyDb2.</span><span class="sxs-lookup"><span data-stu-id="b47e6-199">The following code example creates a transaction log backup on MyDb1 and on MyDb2.</span></span>  
  
    ```sql
    -- On the server instance that hosts the primary replica,   
    -- Backup the transaction log on each primary database:  
    BACKUP LOG MyDb1   
    TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH NOFORMAT  
    GO  
  
    BACKUP LOG MyDb2   
    TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITHNOFORMAT  
    GO
    ```  
  
    > [!TIP]  
    >  <span data-ttu-id="b47e6-200">Normalmente, debe realizarse una copia de seguridad de registros en cada base de datos principal y, después, restaurarse en la base de datos secundaria correspondiente (utilizando WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="b47e6-200">Typically, a log backup must be taken on each primary database and then restored on the corresponding secondary database (using WITH NORECOVERY).</span></span> <span data-ttu-id="b47e6-201">Sin embargo, puede que no se necesite esta copia de seguridad de registros si la base de datos se ha creado recientemente y no se ha realizado todavía ninguna copia de seguridad de registros, o si el modelo de recuperación ha cambiado recientemente de SIMPLE a FULL.</span><span class="sxs-lookup"><span data-stu-id="b47e6-201">However, this log backup might be unnecessary if the database has just been created and no log backup has been taken yet or the recovery model has just been changed from SIMPLE to FULL.</span></span>  
  
8.  <span data-ttu-id="b47e6-202">En la instancia del servidor que hospeda la réplica secundaria, aplique las copias de seguridad de registros a las bases de datos secundarias.</span><span class="sxs-lookup"><span data-stu-id="b47e6-202">On the server instance that hosts the secondary replica, apply log backups to the secondary databases.</span></span>  
  
     <span data-ttu-id="b47e6-203">En el ejemplo de código siguiente se aplican copias de seguridad a las bases de datos secundarias *MyDb1* y *MyDb2* mediante la restauración de las copias de seguridad de base de datos con RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="b47e6-203">The following code example applies backups to *MyDb1* and *MyDb2* secondary databases by restoring database backups using RESTORE WITH NORECOVERY.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b47e6-204">Cuando se prepara una base de datos secundaria real, es necesario aplicar cada copia de seguridad de registros desde la copia de seguridad de base de datos a partir de la cual se creó la base de datos secundaria, empezando por la más temprana y utilizando siempre RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="b47e6-204">When you are preparing a real secondary database, you need to apply every log backup taken since the database backup from which you created the secondary database, starting with the earliest and always using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="b47e6-205">Por supuesto, si restaura tanto la copia de seguridad diferencial como la copia de seguridad completa de bases de datos, solo tendría que aplicar las copias de seguridad de registros realizadas después de la copia de seguridad diferencial.</span><span class="sxs-lookup"><span data-stu-id="b47e6-205">Of course, if you restore both full and differential database backups, you would only need to apply the log backups taken after the differential backup.</span></span>  
  
    ```sql
    -- Restore the transaction log on each secondary database,  
    -- using the WITH NORECOVERY option:  
    RESTORE LOG MyDb1   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    RESTORE LOG MyDb2   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
9. <span data-ttu-id="b47e6-206">En la instancia del servidor que hospeda la réplica secundaria, combine las nuevas bases de datos secundarias al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b47e6-206">On the server instance that hosts the secondary replica, join the new secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="b47e6-207">En el ejemplo de código siguiente se une la base de datos secundaria *MyDb1* y luego la base de datos secundaria *MyDb2* al grupo de disponibilidad *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="b47e6-207">The following code example, joins the *MyDb1* secondary database and then the *MyDb2* secondary databases to the *MyAG* availability group.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- join each secondary database to the availability group:  
    ALTER DATABASE MyDb1 SET HADR AVAILABILITY GROUP = MyAG;  
    GO  
  
    ALTER DATABASE MyDb2 SET HADR AVAILABILITY GROUP = MyAG;  
    GO
    ```  
  
###  <a name="complete-code-example-for-sample-configuration-procedure"></a><a name="CompleteCodeExample"></a> <span data-ttu-id="b47e6-208">Ejemplo completo de código del procedimiento de configuración de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b47e6-208">Complete Code Example for Sample Configuration Procedure</span></span>  
 <span data-ttu-id="b47e6-209">En el ejemplo siguiente se unen los ejemplos de código de todos los pasos del procedimiento de configuración de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b47e6-209">The following example merges the code examples from all the steps of the sample configuration procedure.</span></span> <span data-ttu-id="b47e6-210">En la tabla siguiente se resumen los valores de marcador de posición utilizados en este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="b47e6-210">The following table summarized the placeholder values used in this code example.</span></span> <span data-ttu-id="b47e6-211">Para obtener más información acerca de los pasos de este ejemplo de código, vea [Requisitos previos para usar el procedimiento de configuración de ejemplo](#PrerequisitesForExample) y [Procedimiento de configuración de ejemplo](#SampleProcedure), anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="b47e6-211">For more information about the steps in this code example, see [Prerequisites for Using the Sample Configuration Procedure](#PrerequisitesForExample) and [Sample Configuration Procedure](#SampleProcedure), earlier in this topic.</span></span>  
  
|<span data-ttu-id="b47e6-212">Marcador de posición</span><span class="sxs-lookup"><span data-stu-id="b47e6-212">Placeholder</span></span>|<span data-ttu-id="b47e6-213">Descripción</span><span class="sxs-lookup"><span data-stu-id="b47e6-213">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b47e6-214">\\\\*FILESERVER*\\*SQLbackups*</span><span class="sxs-lookup"><span data-stu-id="b47e6-214">\\\\*FILESERVER*\\*SQLbackups*</span></span>|<span data-ttu-id="b47e6-215">Recurso compartido de copia de seguridad ficticio.</span><span class="sxs-lookup"><span data-stu-id="b47e6-215">Fictional backup share.</span></span>|  
|<span data-ttu-id="b47e6-216">\\\\*FILESERVER*\\*SQLbackups\MyDb1.bak*</span><span class="sxs-lookup"><span data-stu-id="b47e6-216">\\\\*FILESERVER*\\*SQLbackups\MyDb1.bak*</span></span>|<span data-ttu-id="b47e6-217">Archivo de copia de seguridad de MyDb1.</span><span class="sxs-lookup"><span data-stu-id="b47e6-217">Backup file for MyDb1.</span></span>|  
|<span data-ttu-id="b47e6-218">\\\\*FILESERVER*\\*SQLbackups\MyDb2.bak*</span><span class="sxs-lookup"><span data-stu-id="b47e6-218">\\\\*FILESERVER*\\*SQLbackups\MyDb2.bak*</span></span>|<span data-ttu-id="b47e6-219">Archivo de copia de seguridad de MyDb2.</span><span class="sxs-lookup"><span data-stu-id="b47e6-219">Backup file for MyDb2.</span></span>|  
|<span data-ttu-id="b47e6-220">*7022*</span><span class="sxs-lookup"><span data-stu-id="b47e6-220">*7022*</span></span>|<span data-ttu-id="b47e6-221">Número de puerto asignado a cada extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b47e6-221">Port number assigned to each database mirroring endpoint.</span></span>|  
|<span data-ttu-id="b47e6-222">*COMPUTER01\AgHostInstance*</span><span class="sxs-lookup"><span data-stu-id="b47e6-222">*COMPUTER01\AgHostInstance*</span></span>|<span data-ttu-id="b47e6-223">Instancia del servidor que hospeda la réplica principal inicial.</span><span class="sxs-lookup"><span data-stu-id="b47e6-223">Server instance that hosts the initial primary replica.</span></span>|  
|<span data-ttu-id="b47e6-224">*COMPUTER02*</span><span class="sxs-lookup"><span data-stu-id="b47e6-224">*COMPUTER02*</span></span>|<span data-ttu-id="b47e6-225">Instancia del servidor que hospeda la réplica secundaria inicial.</span><span class="sxs-lookup"><span data-stu-id="b47e6-225">Server instance that hosts the initial secondary replica.</span></span> <span data-ttu-id="b47e6-226">Esta es la instancia del servidor predeterminada en `COMPUTER02`.</span><span class="sxs-lookup"><span data-stu-id="b47e6-226">This is the default server instance on `COMPUTER02`.</span></span>|  
|<span data-ttu-id="b47e6-227">*dbm_endpoint*</span><span class="sxs-lookup"><span data-stu-id="b47e6-227">*dbm_endpoint*</span></span>|<span data-ttu-id="b47e6-228">Nombre especificado para cada extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b47e6-228">Name specified for each database mirroring endpoint.</span></span>|  
|<span data-ttu-id="b47e6-229">*MyAG*</span><span class="sxs-lookup"><span data-stu-id="b47e6-229">*MyAG*</span></span>|<span data-ttu-id="b47e6-230">Nombre del grupo de disponibilidad de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b47e6-230">Name of sample availability group.</span></span>|  
|<span data-ttu-id="b47e6-231">*MyDb1*</span><span class="sxs-lookup"><span data-stu-id="b47e6-231">*MyDb1*</span></span>|<span data-ttu-id="b47e6-232">Nombre de la primera base de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b47e6-232">Name of first sample database.</span></span>|  
|<span data-ttu-id="b47e6-233">*MyDb2*</span><span class="sxs-lookup"><span data-stu-id="b47e6-233">*MyDb2*</span></span>|<span data-ttu-id="b47e6-234">Nombre de la segunda base de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b47e6-234">Name of second sample database.</span></span>|  
|<span data-ttu-id="b47e6-235">*DOMAIN1\user1*</span><span class="sxs-lookup"><span data-stu-id="b47e6-235">*DOMAIN1\user1*</span></span>|<span data-ttu-id="b47e6-236">Cuenta de servicio de la instancia del servidor que va a hospedar la réplica principal inicial.</span><span class="sxs-lookup"><span data-stu-id="b47e6-236">Service account of the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="b47e6-237">*DOMAIN2\user2*</span><span class="sxs-lookup"><span data-stu-id="b47e6-237">*DOMAIN2\user2*</span></span>|<span data-ttu-id="b47e6-238">Cuenta de servicio de la instancia del servidor que va a hospedar la réplica secundaria inicial.</span><span class="sxs-lookup"><span data-stu-id="b47e6-238">Service account of the server instance that is to host the initial secondary replica.</span></span>|  
|<span data-ttu-id="b47e6-239">TCP://*COMPUTER01.Adventure-Works.com*:*7022*</span><span class="sxs-lookup"><span data-stu-id="b47e6-239">TCP://*COMPUTER01.Adventure-Works.com*:*7022*</span></span>|<span data-ttu-id="b47e6-240">Dirección URL de la instancia AgHostInstance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en COMPUTER01.</span><span class="sxs-lookup"><span data-stu-id="b47e6-240">Endpoint URL of the AgHostInstance instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on COMPUTER01.</span></span>|  
|<span data-ttu-id="b47e6-241">TCP://*COMPUTER02.Adventure-Works.com*:*5022*</span><span class="sxs-lookup"><span data-stu-id="b47e6-241">TCP://*COMPUTER02.Adventure-Works.com*:*5022*</span></span>|<span data-ttu-id="b47e6-242">Dirección URL del extremo de la instancia predeterminada de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en COMPUTER02.</span><span class="sxs-lookup"><span data-stu-id="b47e6-242">Endpoint URL of the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on COMPUTER02.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="b47e6-243">Para obtener ejemplos adicionales de código [!INCLUDE[tsql](../../../includes/tsql-md.md)] para la creación de un grupo de disponibilidad, vea [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b47e6-243">For additional [!INCLUDE[tsql](../../../includes/tsql-md.md)] code examples of creating an availability group, see [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span></span>  
  
```sql
-- on the server instance that will host the primary replica,   
-- create sample databases:  
CREATE DATABASE MyDb1;  
GO  
ALTER DATABASE MyDb1 SET RECOVERY FULL;  
GO  
  
CREATE DATABASE MyDb2;  
GO  
ALTER DATABASE MyDb2 SET RECOVERY FULL;  
GO  
  
-- Backup sample databases:  
BACKUP DATABASE MyDb1   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH FORMAT  
GO  
  
BACKUP DATABASE MyDb2   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH FORMAT  
GO  
  
-- Create the endpoint on the server instance that will host the primary replica:  
CREATE ENDPOINT dbm_endpoint  
    STATE=STARTED   
    AS TCP (LISTENER_PORT=7022)   
    FOR DATABASE_MIRRORING (ROLE=ALL)  
GO  
  
-- Create the endpoint on the server instance that will host the secondary replica:   
CREATE ENDPOINT dbm_endpoint  
    STATE=STARTED   
    AS TCP (LISTENER_PORT=7022)   
    FOR DATABASE_MIRRORING (ROLE=ALL)  
GO  
  
-- If both service accounts run under the same domain account, skip this step. Otherwise,   
-- On the server instance that will host the primary replica,   
-- create a login for the service account   
-- of the server instance that will host the secondary replica, DOMAIN2\user2,   
-- and grant this login connect permissions on the endpoint:  
USE master;  
GO  
CREATE LOGIN [DOMAIN2\user2] FROM WINDOWS;  
GO  
GRANT CONNECT ON ENDPOINT::dbm_endpoint   
   TO [DOMAIN2\user2];  
GO  
  
-- If both service accounts run under the same domain account, skip this step. Otherwise,   
-- On the server instance that will host the secondary replica,  
-- create a login for the service account   
-- of the server instance that will host the primary replica, DOMAIN1\user1,   
-- and grant this login connect permissions on the endpoint:  
USE master;  
GO  
  
CREATE LOGIN [DOMAIN1\user1] FROM WINDOWS;  
GO  
GRANT CONNECT ON ENDPOINT::dbm_endpoint   
   TO [DOMAIN1\user1];  
GO  
  
-- On the server instance that will host the primary replica,   
-- create the availability group, MyAG:  
CREATE AVAILABILITY GROUP MyAG   
   FOR   
      DATABASE MyDB1, MyDB2   
   REPLICA ON   
      'COMPUTER01\AgHostInstance' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER01.Adventure-Works.com:7022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = AUTOMATIC  
         ),  
      'COMPUTER02' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER02.Adventure-Works.com:7022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = AUTOMATIC  
         );   
GO  
  
-- On the server instance that hosts the secondary replica,   
-- join the secondary replica to the availability group:  
ALTER AVAILABILITY GROUP MyAG JOIN;  
GO  
  
-- Restore database backups onto this server instance, using RESTORE WITH NORECOVERY:  
RESTORE DATABASE MyDb1   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH NORECOVERY  
GO  
  
RESTORE DATABASE MyDb2   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH NORECOVERY  
GO  
  
-- Back up the transaction log on each primary database:  
BACKUP LOG MyDb1   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH NOFORMAT  
GO  
  
BACKUP LOG MyDb2   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITHNOFORMAT  
GO  
  
-- Restore the transaction log on each secondary database,  
-- using the WITH NORECOVERY option:  
RESTORE LOG MyDb1   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH FILE=1, NORECOVERY  
GO  
RESTORE LOG MyDb2   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH FILE=1, NORECOVERY  
GO  
  
-- On the server instance that hosts the secondary replica,   
-- join each secondary database to the availability group:  
ALTER DATABASE MyDb1 SET HADR AVAILABILITY GROUP = MyAG;  
GO  
  
ALTER DATABASE MyDb2 SET HADR AVAILABILITY GROUP = MyAG;  
GO
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b47e6-244">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="b47e6-244">Related Tasks</span></span>  
 <span data-ttu-id="b47e6-245">**Para configurar el grupo de disponibilidad y las propiedades de réplica**</span><span class="sxs-lookup"><span data-stu-id="b47e6-245">**To configure availability group and replica properties**</span></span>  
  
-   [<span data-ttu-id="b47e6-246">Cambiar el modo de disponibilidad de una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-246">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="b47e6-247">Cambiar el modo de conmutación por error de una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-247">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="b47e6-248">Crear o configurar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-248">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="b47e6-249">Configurar la directiva de conmutación por error flexible para controlar las condiciones de la conmutación automática por error (grupos de disponibilidad AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="b47e6-249">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="b47e6-250">Especificar la dirección URL del punto de conexión al agregar o modificar una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-250">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="b47e6-251">Configurar la copia de seguridad en réplicas de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-251">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="b47e6-252">Configurar el acceso de solo lectura en una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-252">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="b47e6-253">Configurar el enrutamiento de solo lectura para un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-253">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="b47e6-254">Cambiar el tiempo de espera de la sesión en una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-254">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="b47e6-255">**Para completar la configuración del grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="b47e6-255">**To complete availability group configuration**</span></span>  
  
-   [<span data-ttu-id="b47e6-256">Combinar una réplica secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-256">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="b47e6-257">Preparar manualmente una base de datos secundaria para un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-257">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="b47e6-258">Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-258">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="b47e6-259">Crear o configurar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-259">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
 <span data-ttu-id="b47e6-260">**Maneras alternativas de crear un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="b47e6-260">**Alternative ways to create an availability group**</span></span>  
  
-   [<span data-ttu-id="b47e6-261">Usar el Asistente para grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-261">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="b47e6-262">Usar el cuadro de diálogo Nuevo grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-262">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="b47e6-263">Crear un grupo de disponibilidad &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-263">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
 <span data-ttu-id="b47e6-264">**Para habilitar los grupos de disponibilidad de AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="b47e6-264">**To enable AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="b47e6-265">Habilitar y deshabilitar grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-265">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="b47e6-266">**Para configurar un extremo de creación del reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="b47e6-266">**To configure a database mirroring endpoint**</span></span>  
  
-   [<span data-ttu-id="b47e6-267">Cree un extremo de creación de reflejo de la base de datos para Grupos de disponibilidad AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-267">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="b47e6-268">Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-268">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="b47e6-269">Usar certificados para un punto de conexión de creación de reflejo de la base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-269">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
-   [<span data-ttu-id="b47e6-270">Especificar la dirección URL del punto de conexión al agregar o modificar una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-270">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="b47e6-271">**Para solucionar de problemas de configuración de grupos de disponibilidad de AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="b47e6-271">**To troubleshoot AlwaysOn Availability Groups configuration**</span></span>  
  
-   [<span data-ttu-id="b47e6-272">Solucionar problemas de configuración de Grupos de disponibilidad AlwaysOn (SQL Server) eliminada</span><span class="sxs-lookup"><span data-stu-id="b47e6-272">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="b47e6-273">Solucionar problemas de una operación Add-File &#40;Grupos de disponibilidad AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-273">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="b47e6-274">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="b47e6-274">Related Content</span></span>  
  
-   <span data-ttu-id="b47e6-275">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="b47e6-275">**Blogs:**</span></span>  
  
     [<span data-ttu-id="b47e6-276">Series de aprendizaje de AlwaysON - HADRON: uso del grupo de trabajo para las bases de datos compatibles con HADRON</span><span class="sxs-lookup"><span data-stu-id="b47e6-276">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="b47e6-277">Blogs del equipo de AlwaysOn de SQL Server: el blog oficial del equipo de AlwaysOn de SQL Server</span><span class="sxs-lookup"><span data-stu-id="b47e6-277">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="b47e6-278">Blogs de los ingenieros de SQL Server de CSS</span><span class="sxs-lookup"><span data-stu-id="b47e6-278">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="b47e6-279">**Vídeos:**</span><span class="sxs-lookup"><span data-stu-id="b47e6-279">**Videos:**</span></span>  
  
     [<span data-ttu-id="b47e6-280">Microsoft SQL Server Code-Named "Denali", Serie AlwaysOn, parte 1: Introducción a la solución de alta disponibilidad de siguiente generación</span><span class="sxs-lookup"><span data-stu-id="b47e6-280">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="b47e6-281">Microsoft SQL Server “Denali”, Serie AlwaysOn, parte 2: Crear una solución esencial de alta disponibilidad utilizando AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="b47e6-281">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="b47e6-282">**Notas del producto:**</span><span class="sxs-lookup"><span data-stu-id="b47e6-282">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="b47e6-283">Guía de soluciones AlwaysOn de Microsoft SQL Server para lograr alta disponibilidad y recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="b47e6-283">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="b47e6-284">Notas del producto de Microsoft para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="b47e6-284">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="b47e6-285">Notas del producto del equipo de asesoramiento al cliente de SQL Server</span><span class="sxs-lookup"><span data-stu-id="b47e6-285">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="b47e6-286">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b47e6-286">See Also</span></span>  
 <span data-ttu-id="b47e6-287">[El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b47e6-287">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="b47e6-288">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b47e6-288">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="b47e6-289">Agentes de escucha de grupo de disponibilidad, conectividad de cliente y conmutación por error de una aplicación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b47e6-289">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)   
