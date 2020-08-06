---
title: Administración de un grupo de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], managing
ms.assetid: 0b7542fa-235e-413d-81bf-3eff9ee07480
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2cac9a34fe71c11f71ec47bbb6d690199869fef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663721"
---
# <a name="administration-of-an-availability-group-sql-server"></a><span data-ttu-id="34905-102">Administración de un grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="34905-102">Administration of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="34905-103">La administración de un grupo de disponibilidad AlwaysOn en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] implica una o varias de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="34905-103">Managing an existing AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] involves one or more of the following tasks:</span></span>  
  
-   <span data-ttu-id="34905-104">Modificar las propiedades de una réplica de disponibilidad existente, por ejemplo para cambiar el acceso de la conexión de cliente (para configurar réplicas secundarias legibles), cambiar el modo de conmutación por error, el modo de disponibilidad o el valor de tiempo de espera de la sesión.</span><span class="sxs-lookup"><span data-stu-id="34905-104">Altering the properties of an existing availability replica, for example to change client connection access (for configuring readable secondary replicas), changing its failover mode, availability mode, or session timeout setting.</span></span>  
  
-   <span data-ttu-id="34905-105">Agregar o quitar réplicas secundarias.</span><span class="sxs-lookup"><span data-stu-id="34905-105">Adding or removing secondary replicas.</span></span>  
  
-   <span data-ttu-id="34905-106">Agregar o quitar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="34905-106">Adding or removing a database.</span></span>  
  
-   <span data-ttu-id="34905-107">Suspender o reanudar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="34905-107">Suspending or resuming a database.</span></span>  
  
-   <span data-ttu-id="34905-108">Realizar una conmutación por error manual planeada (una *conmutación por error manual*) o una conmutación por error manual forzada (una *conmutación por error forzada*).</span><span class="sxs-lookup"><span data-stu-id="34905-108">Performing a planned manual failover (a *manual failover*) or a forced manual failover (a *forced failover*).</span></span>  
  
-   <span data-ttu-id="34905-109">Crear o configurar un agente de escucha del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="34905-109">Creating or configuring an availability group listener.</span></span>  
  
-   <span data-ttu-id="34905-110">Administrar [réplicas secundarias legibles](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) para un grupo de disponibilidad determinado.</span><span class="sxs-lookup"><span data-stu-id="34905-110">Managing [readable secondary replicas](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) for a given availability group.</span></span> <span data-ttu-id="34905-111">Esto implica la configuración de una o varias replica el acceso de solo lectura al ejecutar con rol secundario, y la configuración de enrutamiento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="34905-111">This involves configuring one or more replicas to read-only access when running under the secondary role, and configuring read-only routing.</span></span>  
  
-   <span data-ttu-id="34905-112">Administrar [copias de seguridad en las réplicas secundarias](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) para un grupo de disponibilidad determinado.</span><span class="sxs-lookup"><span data-stu-id="34905-112">Managing [backups on secondary replicas](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) for a given availability group.</span></span> <span data-ttu-id="34905-113">Esto implica configurar desde donde prefiera que se ejecuten los trabajos de copia de seguridad y despues incluir en scripts los trabajos de copia de seguridad para implementar sus preferencias de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="34905-113">This involves configuring where you prefer that backup jobs run and then scripting backup jobs to implement your backup preference.</span></span> <span data-ttu-id="34905-114">necesita los trabajos de copia de seguridad de script para cada base de datos del grupo de la disponibilidad en cada instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda una réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="34905-114">you need to script backup jobs for every database in the availability group on every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts an availability replica.</span></span>  
  
-   <span data-ttu-id="34905-115">Eliminar un grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="34905-115">Deleting an availability group.</span></span>  
  
-   <span data-ttu-id="34905-116">Migración entre clústeres de grupos de disponibilidad AlwaysOn para la actualización del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="34905-116">Cross-cluster migration of AlwaysOn Availability Groups for OS upgrade</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="34905-117">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="34905-117">Related Tasks</span></span>  
 <span data-ttu-id="34905-118">**Para configurar un grupo de disponibilidad existente**</span><span class="sxs-lookup"><span data-stu-id="34905-118">**To configure an existing availability group**</span></span>  
  
-   [<span data-ttu-id="34905-119">Agregar una réplica secundaria a un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-119">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="34905-120">Quitar una réplica secundaria de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-120">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="34905-121">Agregar una base de datos a un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-121">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="34905-122">Quitar una base de datos secundaria de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-122">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="34905-123">Quitar una base de datos principal de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-123">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="34905-124">Configure la Directiva de conmutación por error flexible para controlar las condiciones de la conmutación por error automática &#40;Grupos de disponibilidad AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-124">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover &#40;AlwaysOn Availability Groups&#41;</span></span>](configure-flexible-automatic-failover-policy.md)  
  
 <span data-ttu-id="34905-125">**Para administrar un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="34905-125">**To manage an availability group**</span></span>  
  
-   [<span data-ttu-id="34905-126">Configurar la copia de seguridad en réplicas de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-126">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="34905-127">Realizar una conmutación por error manual planeada de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-127">Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="34905-128">Realizar una conmutación por error manual forzada de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-128">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="34905-129">Quitar un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-129">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="34905-130">**Para administrar una réplica de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="34905-130">**To manage an availability replica**</span></span>  
  
-   [<span data-ttu-id="34905-131">Agregar una réplica secundaria a un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-131">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="34905-132">Combinar una réplica secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-132">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="34905-133">Quitar una réplica secundaria de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-133">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="34905-134">Cambiar el modo de disponibilidad de una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-134">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="34905-135">Cambiar el modo de conmutación por error de una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-135">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="34905-136">Configurar la copia de seguridad en réplicas de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-136">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="34905-137">Configurar el acceso de solo lectura en una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-137">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="34905-138">Configurar el enrutamiento de solo lectura para un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-138">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="34905-139">Cambiar el tiempo de espera de la sesión en una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-139">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="34905-140">**Para administrar una base de datos de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="34905-140">**To manage an availability database**</span></span>  
  
-   [<span data-ttu-id="34905-141">Agregar una base de datos a un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-141">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="34905-142">Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-142">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="34905-143">Quitar una base de datos principal de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-143">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="34905-144">Quitar una base de datos secundaria de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-144">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="34905-145">Suspender una base de datos de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-145">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="34905-146">Reanudar una base de datos de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-146">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
 <span data-ttu-id="34905-147">**Para supervisar un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="34905-147">**To monitor an availability group**</span></span>  
  
-   [<span data-ttu-id="34905-148">Herramientas para supervisar grupos de disponibilidad Always On &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-148">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
 <span data-ttu-id="34905-149">**Para admitir la migración de grupos de disponibilidad a un nuevo clúster de WSFC (migración entre clústeres)**</span><span class="sxs-lookup"><span data-stu-id="34905-149">**To support migrating availability groups to a new WSFC cluster (cross-cluster migration)**</span></span>  
  
-   [<span data-ttu-id="34905-150">Cambiar el contexto de clúster de HADR de la instancia de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-150">Change the HADR Cluster Context of Server Instance &#40;SQL Server&#41;</span></span>](change-the-hadr-cluster-context-of-server-instance-sql-server.md)  
  
-   [<span data-ttu-id="34905-151">Poner sin conexión un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-151">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)  
  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="34905-152">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="34905-152">Related Content</span></span>  
  
-   <span data-ttu-id="34905-153">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="34905-153">**Blogs:**</span></span>  
  
     [<span data-ttu-id="34905-154">Blogs del equipo de AlwaysOn de SQL Server: el blog oficial del equipo de AlwaysOn de SQL Server</span><span class="sxs-lookup"><span data-stu-id="34905-154">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="34905-155">Blogs de los ingenieros de SQL Server de CSS</span><span class="sxs-lookup"><span data-stu-id="34905-155">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="34905-156">**Vídeos:**</span><span class="sxs-lookup"><span data-stu-id="34905-156">**Videos:**</span></span>  
  
     [<span data-ttu-id="34905-157">Microsoft SQL Server Code-Named "Denali", Serie AlwaysOn, parte 1: Introducción a la solución de alta disponibilidad de siguiente generación</span><span class="sxs-lookup"><span data-stu-id="34905-157">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="34905-158">Microsoft SQL Server “Denali”, Serie AlwaysOn, parte 2: Crear una solución esencial de alta disponibilidad utilizando AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="34905-158">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="34905-159">**Notas del producto:**</span><span class="sxs-lookup"><span data-stu-id="34905-159">**White papers:**</span></span>  
  
     [<span data-ttu-id="34905-160">Notas del producto de Microsoft para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="34905-160">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="34905-161">Notas del producto del equipo de asesoramiento al cliente de SQL Server</span><span class="sxs-lookup"><span data-stu-id="34905-161">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
  
## <a name="see-also"></a><span data-ttu-id="34905-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34905-162">See Also</span></span>  
 <span data-ttu-id="34905-163">[Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34905-163">[AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="34905-164">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34905-164">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="34905-165">Configuración de una instancia de servidor para Grupos de disponibilidad AlwaysOn SQL Server de &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-165">Configuration of a Server Instance for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](configuration-of-a-server-instance-for-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="34905-166">[Creación y configuración de grupos de disponibilidad &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34905-166">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="34905-167">[Secundarias activas: réplicas secundarias legibles &#40;Grupos de disponibilidad AlwaysOn&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="34905-167">[Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="34905-168">Secundarias activas: copia de seguridad en las réplicas secundarias &#40;Grupos de disponibilidad AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-168">Active Secondaries: Backup on Secondary Replicas &#40;AlwaysOn Availability Groups&#41;</span></span>](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md)  
 <span data-ttu-id="34905-169">[Agentes de escucha de grupo de disponibilidad, conectividad de cliente y conmutación por error de una aplicación &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="34905-169">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 <span data-ttu-id="34905-170">[Directivas de AlwaysOn para problemas operativos con Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="34905-170">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 <span data-ttu-id="34905-171">[Supervisión de los grupos de disponibilidad &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34905-171">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="34905-172">[Grupos de disponibilidad AlwaysOn: SQL Server de &#40;de interoperabilidad&#41;](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34905-172">[AlwaysOn Availability Groups: Interoperability &#40;SQL Server&#41;](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 <span data-ttu-id="34905-173">[Información general sobre las instrucciones Transact-SQL para Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](transact-sql-statements-for-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="34905-173">[Overview of Transact-SQL Statements for AlwaysOn Availability Groups &#40;SQL Server&#41;](transact-sql-statements-for-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="34905-174">Información general de los cmdlets de PowerShell para Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34905-174">Overview of PowerShell Cmdlets for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-powershell-cmdlets-for-always-on-availability-groups-sql-server.md)  
  
