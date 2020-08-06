---
title: Creación y configuración de grupos de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], creating
ms.assetid: 7f89fab8-6ee2-4273-9de0-e594bfb9407f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bc33da393527c19985f5e7b214ba4bc02dc2f3af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752342"
---
# <a name="creation-and-configuration-of-availability-groups-sql-server"></a><span data-ttu-id="f9266-102">Creación y configuración de grupos de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f9266-102">Creation and Configuration of Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="f9266-103">Los temas de esta sección explican la forma de implementar una implementación de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] en instancias de [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] que residen en nodos diferentes de clústeres de conmutación por error de Windows Server (WSFC) dentro de un único clúster de conmutación por error de WSFC.</span><span class="sxs-lookup"><span data-stu-id="f9266-103">The topics in this section explain how to deploy a [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] implementation on instances of [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] that reside on different Windows Server Failover Clustering (WSFC) nodes within a single WSFC failover cluster.</span></span>  
  
 <span data-ttu-id="f9266-104">Antes de crear el primer grupo de disponibilidad, se recomienda encarecidamente que se familiarice con la información de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f9266-104">Before you create your first availability group, we strongly recommend that you familiarize yourself with the information in the following topics:</span></span>  
  
 [<span data-ttu-id="f9266-105">Requisitos previos, restricciones y recomendaciones para el SQL Server de &#40;de Grupos de disponibilidad AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-105">Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-restrictions-recommendations-always-on-availability.md)  
 <span data-ttu-id="f9266-106">En este tema se describen los requisitos previos, restricciones y recomendaciones para equipos; los nodos de WSFC; las instancias de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; los grupos, réplicas y bases de datos de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f9266-106">This topic describes the prerequisites, restrictions, and recommendations for computers; WSFC nodes; instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; availability groups, replicas, and databases.</span></span> <span data-ttu-id="f9266-107">Este tema también contiene información sobre consideraciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f9266-107">This topic also contains information about security considerations.</span></span>  
  
 [<span data-ttu-id="f9266-108">Introducción con Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-108">Getting Started with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](getting-started-with-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="f9266-109">Incluye información sobre los pasos para configurar una instancia de servidor, crear un grupo de disponibilidad, configurar el grupo de disponibilidad para las conexiones de cliente, administrar los grupos de disponibilidad y supervisar los grupos de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f9266-109">Contains information about the steps for configuring a server instance, creating an availability group, configuring the availability group for client connections, managing availability groups, and monitoring availability groups.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f9266-110">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="f9266-110">Related Tasks</span></span>  
 <span data-ttu-id="f9266-111">**Para configurar una instancia del servidor para [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="f9266-111">**To configure a server instance for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]**</span></span>  
  
-   [<span data-ttu-id="f9266-112">Habilitar y deshabilitar grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-112">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="f9266-113">Cree un extremo de creación de reflejo de la base de datos para Grupos de disponibilidad AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-113">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="f9266-114">Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-114">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="f9266-115">Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones salientes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-115">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
 <span data-ttu-id="f9266-116">**Para comenzar a configurar los grupos de disponibilidad AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f9266-116">**To get started with configuring AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="f9266-117">Introducción con Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-117">Getting Started with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](getting-started-with-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="f9266-118">**Para crear y configurar un nuevo grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="f9266-118">**To create and configure a new availability group**</span></span>  
  
-   [<span data-ttu-id="f9266-119">Usar el Asistente para grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-119">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="f9266-120">Crear un grupo de disponibilidad &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-120">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="f9266-121">Crear un grupo de disponibilidad &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-121">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="f9266-122">Usar el cuadro de diálogo Nuevo grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-122">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="f9266-123">Especificar la dirección URL del punto de conexión al agregar o modificar una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-123">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="f9266-124">Crear o configurar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-124">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="f9266-125">Configurar la directiva de conmutación por error flexible para controlar las condiciones de la conmutación automática por error (grupos de disponibilidad AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="f9266-125">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="f9266-126">Configurar la copia de seguridad en réplicas de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-126">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="f9266-127">Configurar el acceso de solo lectura en una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-127">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="f9266-128">Configurar el enrutamiento de solo lectura para un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-128">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f9266-129">Combinar una réplica secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-129">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f9266-130">Iniciar el movimiento de datos en una base de datos secundaria AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-130">Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;</span></span>](start-data-movement-on-an-always-on-secondary-database-sql-server.md)  
  
-   [<span data-ttu-id="f9266-131">Preparar manualmente una base de datos secundaria para un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-131">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f9266-132">Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-132">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f9266-133">Administración de inicios de sesión y de trabajos para las bases de datos de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-133">Management of Logins and Jobs for the Databases of an Availability Group &#40;SQL Server&#41;</span></span>](../../logins-and-jobs-for-availability-group-databases.md)  
  
 <span data-ttu-id="f9266-134">**Para solucionar problemas**</span><span class="sxs-lookup"><span data-stu-id="f9266-134">**To troubleshoot**</span></span>  
  
-   [<span data-ttu-id="f9266-135">Solucionar problemas de configuración de Grupos de disponibilidad AlwaysOn (SQL Server) eliminada</span><span class="sxs-lookup"><span data-stu-id="f9266-135">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="f9266-136">Solucionar problemas de una operación Add-File &#40;Grupos de disponibilidad AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="f9266-136">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="f9266-137">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="f9266-137">Related Content</span></span>  
  
-   <span data-ttu-id="f9266-138">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="f9266-138">**Blogs:**</span></span>  
  
     [<span data-ttu-id="f9266-139">Series de aprendizaje de AlwaysON - HADRON: uso del grupo de trabajo para las bases de datos compatibles con HADRON</span><span class="sxs-lookup"><span data-stu-id="f9266-139">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="f9266-140">Blogs del equipo de AlwaysOn de SQL Server: el blog oficial del equipo de AlwaysOn de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9266-140">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="f9266-141">Blogs de los ingenieros de SQL Server de CSS</span><span class="sxs-lookup"><span data-stu-id="f9266-141">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="f9266-142">**Vídeos:**</span><span class="sxs-lookup"><span data-stu-id="f9266-142">**Videos:**</span></span>  
  
     [<span data-ttu-id="f9266-143">Microsoft SQL Server Code-Named "Denali", Serie AlwaysOn, parte 1: Introducción a la solución de alta disponibilidad de siguiente generación</span><span class="sxs-lookup"><span data-stu-id="f9266-143">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="f9266-144">Microsoft SQL Server “Denali”, Serie AlwaysOn, parte 2: Crear una solución esencial de alta disponibilidad utilizando AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f9266-144">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="f9266-145">**Notas del producto:**</span><span class="sxs-lookup"><span data-stu-id="f9266-145">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="f9266-146">Guía de soluciones AlwaysOn de Microsoft SQL Server para lograr alta disponibilidad y recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="f9266-146">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="f9266-147">Notas del producto de Microsoft para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="f9266-147">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="f9266-148">Notas del producto del equipo de asesoramiento al cliente de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9266-148">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="f9266-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f9266-149">See Also</span></span>  
 <span data-ttu-id="f9266-150">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f9266-150">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="f9266-151">[Administración de un grupo de disponibilidad &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f9266-151">[Administration of an Availability Group &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="f9266-152">[Directivas de AlwaysOn para problemas operativos con Grupos de disponibilidad AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="f9266-152">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 <span data-ttu-id="f9266-153">[Supervisión de los grupos de disponibilidad &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f9266-153">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="f9266-154">Grupos de disponibilidad AlwaysOn: interoperabilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f9266-154">AlwaysOn Availability Groups: Interoperability (SQL Server)</span></span>](always-on-availability-groups-interoperability-sql-server.md)  
  
