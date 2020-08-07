---
title: Requisitos previos para la migración desde el trasvase de registros a Grupos de disponibilidad AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 2738ce65-205e-4682-92d8-dc7e37c58b2b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 76b50d5af8eb520b3764ff56397c040f2d0d0141
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747188"
---
# <a name="prerequisites-for-migrating-from-log-shipping-to-alwayson-availability-groups-sql-server"></a><span data-ttu-id="6c3fb-102">Requisitos previos para migrar desde grupos de trasvase de registros a grupos de disponibilidad AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6c3fb-102">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="6c3fb-103">En este tema se describen los requisitos previos para convertir una base de datos principal de trasvase de registros junto con una o varias de sus bases de datos secundarias en una base de datos principal AlwaysOn y una o varias bases de datos secundarias.</span><span class="sxs-lookup"><span data-stu-id="6c3fb-103">This topic describes the prerequisites for converting a log shipping primary database along with one or more of its secondary databases to an AlwaysOn primary database and secondary database(s).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c3fb-104">Puede configurar cualquier base de datos principal o secundaria (posiblemente legible) de un grupo de disponibilidad como una base de datos principal de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="6c3fb-104">You can configure any primary or secondary database (possibly readable) in an availability group as a log shipping primary database.</span></span>  
  
 <span data-ttu-id="6c3fb-105">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="6c3fb-105">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="6c3fb-106">Requisitos previos de los grupos de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="6c3fb-106">Availability Group Prerequisites</span></span>](#AGPrereqsRealAddress)  
  
-   [<span data-ttu-id="6c3fb-107">Requisitos previos del trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="6c3fb-107">Log Shipping Prerequisites</span></span>](#LogShipPrereqs)  
  
-   [<span data-ttu-id="6c3fb-108">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="6c3fb-108">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="6c3fb-109">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="6c3fb-109">Related Content</span></span>](#RelatedContent)  
  
##  <a name="availability-group-prerequisites"></a><a name="AGPrereqsRealAddress"></a><span data-ttu-id="6c3fb-110">Requisitos previos de los grupos de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="6c3fb-110">Availability Group Prerequisites</span></span>  
 <span data-ttu-id="6c3fb-111">Para permitir los trabajos de copia de seguridad para ejecutarse en la réplica principal del grupo de disponibilidad, use las siguientes opciones de copia de seguridad de los grupos de disponibilidad AlwaysOn:</span><span class="sxs-lookup"><span data-stu-id="6c3fb-111">To allow backup jobs to run on the primary replica of the availability group, use the following AlwaysOn Availability Groups backup settings:</span></span>  
  
|<span data-ttu-id="6c3fb-112">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="6c3fb-112">Property</span></span>|<span data-ttu-id="6c3fb-113">Parámetro</span><span class="sxs-lookup"><span data-stu-id="6c3fb-113">Setting</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="6c3fb-114">Preferencia de la copia de seguridad automatizada del grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="6c3fb-114">Automated backup preference of availability group</span></span>|<span data-ttu-id="6c3fb-115">Solo en la réplica principal</span><span class="sxs-lookup"><span data-stu-id="6c3fb-115">Only on the primary replica</span></span>|  
|<span data-ttu-id="6c3fb-116">Prioridad de copia de seguridad de la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="6c3fb-116">Backup priority of the primary replica.</span></span>|<span data-ttu-id="6c3fb-117">>0</span><span class="sxs-lookup"><span data-stu-id="6c3fb-117">>0</span></span>|  
  
 <span data-ttu-id="6c3fb-118">**Para obtener más información:**</span><span class="sxs-lookup"><span data-stu-id="6c3fb-118">**For more information:**</span></span>  
  
 [<span data-ttu-id="6c3fb-119">Ver las propiedades del grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6c3fb-119">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
 [<span data-ttu-id="6c3fb-120">Configurar la copia de seguridad en réplicas de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6c3fb-120">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
##  <a name="log-shipping-prerequisites"></a><a name="LogShipPrereqs"></a><span data-ttu-id="6c3fb-121">Requisitos previos del trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="6c3fb-121">Log Shipping Prerequisites</span></span>  
  
-   <span data-ttu-id="6c3fb-122">La base de datos principal del trasvase de registros debe residir en la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda la réplica principal actual o inicial del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="6c3fb-122">The log shipping primary database must reside on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the initial/current primary replica of the availability group.</span></span>  
  
-   <span data-ttu-id="6c3fb-123">Para que una base de datos secundaria de trasvase de registros dada se convierta en una base de datos secundaria AlwaysOn, debe:</span><span class="sxs-lookup"><span data-stu-id="6c3fb-123">For a given log shipping secondary database to be converted to an AlwaysOn secondary database, it must:</span></span>  
  
    -   <span data-ttu-id="6c3fb-124">Usar el mismo nombre que la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="6c3fb-124">Use the same name as the primary database.</span></span>  
  
    -   <span data-ttu-id="6c3fb-125">Residir en una instancia del servidor que hospeda una réplica secundaria para el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="6c3fb-125">Reside on a server instance that hosts a secondary replica for the availability group.</span></span>  
  
 <span data-ttu-id="6c3fb-126">Una vez que el trabajo de copia de seguridad se ejecute en la base de datos principal, deshabilite el trabajo de copia de seguridad y, una vez que el trabajo de restauración se haya ejecutado en una base de datos secundaria, deshabilite el trabajo de restauración.</span><span class="sxs-lookup"><span data-stu-id="6c3fb-126">Once the backup job has run on the primary database, disable the backup job, and once the restore job has run on a given secondary database, disable the restore job.</span></span>  
  
 <span data-ttu-id="6c3fb-127">Después de crear todas las bases de datos secundarias para el grupo de disponibilidad, si desea realizar copias de seguridad en las réplicas secundarias, debe configurar de nuevo la preferencia de copia de seguridad automatizada del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="6c3fb-127">After you have created all the secondary databases for the availability group, if you want to perform backups on secondary replicas, you need to re-configure the automated backup preference of the availability group.</span></span>  
  
 <span data-ttu-id="6c3fb-128">**Para obtener más información:**</span><span class="sxs-lookup"><span data-stu-id="6c3fb-128">**For more information:**</span></span>  
  
 <span data-ttu-id="6c3fb-129">[Convertir una configuración de trasvase de registros en un grupo de disponibilidad](https://blogs.msdn.com/b/sqlalwayson/archive/2012/01/09/converting-a-logshipping-configuration-to-availability-group.aspx) (blog de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6c3fb-129">[Converting a logshipping configuration to Availability Group](https://blogs.msdn.com/b/sqlalwayson/archive/2012/01/09/converting-a-logshipping-configuration-to-availability-group.aspx) (a SQL Server blog)</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6c3fb-130">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="6c3fb-130">Related Tasks</span></span>  
 <span data-ttu-id="6c3fb-131">**Trasvase de registros**</span><span class="sxs-lookup"><span data-stu-id="6c3fb-131">**Log shipping**</span></span>  
  
-   [<span data-ttu-id="6c3fb-132">Actualizar el trasvase de registros a SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6c3fb-132">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](../../log-shipping/upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="6c3fb-133">Quitar el trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6c3fb-133">Remove Log Shipping &#40;SQL Server&#41;</span></span>](../../log-shipping/remove-log-shipping-sql-server.md)  
  
 <span data-ttu-id="6c3fb-134">**Grupos de disponibilidad AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="6c3fb-134">**AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="6c3fb-135">Usar el Asistente para grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6c3fb-135">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="6c3fb-136">Usar el cuadro de diálogo Nuevo grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6c3fb-136">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="6c3fb-137">Crear un grupo de disponibilidad &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6c3fb-137">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="6c3fb-138">Crear un grupo de disponibilidad &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="6c3fb-138">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="6c3fb-139">Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6c3fb-139">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="6c3fb-140">Configurar la copia de seguridad en réplicas de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6c3fb-140">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="6c3fb-141">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="6c3fb-141">Related Content</span></span>  
  
-   <span data-ttu-id="6c3fb-142">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="6c3fb-142">**Blogs:**</span></span>  
  
     [<span data-ttu-id="6c3fb-143">Convertir una configuración de trasvase de registros en un grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="6c3fb-143">Converting a logshipping configuration to Availability Group</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/converting-a-logshipping-configuration-to-availability-group)  
  
     [<span data-ttu-id="6c3fb-144">Agregue una base de datos principal de trasvase de registros y una base de datos secundaria a un grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="6c3fb-144">Add a Log Shipping Primary Database and Secondary Database(s) to an Existing Availability Group</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/add-a-log-shipping-primary-database-and-secondary-databases-to-an-existing-availability-group)  
  
     [<span data-ttu-id="6c3fb-145">Blogs del equipo de AlwaysOn de SQL Server: el blog oficial del equipo de AlwaysOn de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6c3fb-145">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/)  
  
     [<span data-ttu-id="6c3fb-146">Blogs de los ingenieros de SQL Server de CSS</span><span class="sxs-lookup"><span data-stu-id="6c3fb-146">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="6c3fb-147">**Notas del producto:**</span><span class="sxs-lookup"><span data-stu-id="6c3fb-147">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="6c3fb-148">Guía de migración: migrar a grupos de disponibilidad AlwaysOn desde implementaciones anteriores que combinan creación de reflejo de la base de datos y trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="6c3fb-148">Migration Guide: Migrating to AlwaysOn Availability Groups from Prior Deployments Combining Database Mirroring and Log Shipping</span></span>](https://msdn.microsoft.com/library/jj635217)  
  
     [<span data-ttu-id="6c3fb-149">Notas del producto de Microsoft para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="6c3fb-149">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="6c3fb-150">Notas del producto del equipo de asesoramiento al cliente de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6c3fb-150">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="6c3fb-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c3fb-151">See Also</span></span>  
 <span data-ttu-id="6c3fb-152">[Acerca del trasvase de registros &#40;SQL Server&#41;](../../log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6c3fb-152">[About Log Shipping &#40;SQL Server&#41;](../../log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="6c3fb-153">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6c3fb-153">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="6c3fb-154">Supervisión de los grupos de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6c3fb-154">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
  
