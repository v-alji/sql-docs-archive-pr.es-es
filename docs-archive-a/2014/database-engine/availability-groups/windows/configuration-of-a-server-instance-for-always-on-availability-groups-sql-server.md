---
title: Configuración de una instancia de servidor para Always On grupos de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], about
ms.assetid: fad8db32-593e-49d5-989c-39eb8399c416
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3392e6189b687516e627d847acceedb165141117
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750213"
---
# <a name="configuration-of-a-server-instance-for-always-on-availability-groups-sql-server"></a><span data-ttu-id="dd0a2-102">Configuración de una instancia del servidor para grupos de disponibilidad AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dd0a2-102">Configuration of a Server Instance for Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="dd0a2-103">Este tema contiene información sobre los requisitos para configurar una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para que se admita [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd0a2-103">This topic contains information about the requirements for configuring an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dd0a2-104">Para obtener información esencial sobre los requisitos previos y las restricciones de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] para los nodos de clústeres de conmutación por error de Windows Server (WSFC) y para las instancias de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], vea [Requisitos previos, restricciones y recomendaciones para Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="dd0a2-104">For essential information about [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] prerequisites and restrictions for Windows Server Failover Clustering (WSFC) nodes and for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
 
  
##  <a name="terms-and-definitions"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="dd0a2-105">Términos y definiciones</span><span class="sxs-lookup"><span data-stu-id="dd0a2-105">Terms and Definitions</span></span>  
  
 <span data-ttu-id="dd0a2-106">Una solución de alta disponibilidad y de recuperación ante desastres que proporciona una alternativa en el nivel de empresa a la creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="dd0a2-106">A high-availability and disaster-recovery solution that provides an enterprise-level replacement for database mirroring.</span></span> <span data-ttu-id="dd0a2-107">Un *grupo de disponibilidad* admite un entorno de conmutación por error para un conjunto discreto de bases de datos de usuario, conocido como *bases de datos de disponibilidad*, que conmutan por error conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="dd0a2-107">An *availability group* supports a failover environment for a discrete set of user databases, known as *availability databases*, that fail over together.</span></span>  
  
 <span data-ttu-id="dd0a2-108">réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="dd0a2-108">availability replica</span></span>  
 <span data-ttu-id="dd0a2-109">Una instancia de un grupo de disponibilidad hospedado en una instancia específica de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y que mantiene una copia local de cada base de datos de disponibilidad perteneciente al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="dd0a2-109">An instantiation of an availability group that is hosted by a specific instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and that maintains a local copy of each availability database that belongs to the availability group.</span></span> <span data-ttu-id="dd0a2-110">Existen dos tipos de réplicas de disponibilidad: una sola *réplica principal* y de una a cuatro *réplicas secundarias*.</span><span class="sxs-lookup"><span data-stu-id="dd0a2-110">Two types of availability replicas exist: a single *primary replica* and one to four *secondary replicas*.</span></span> <span data-ttu-id="dd0a2-111">Las instancias de servidor que hospedan las réplicas de disponibilidad para un grupo de disponibilidad dado deben residir en nodos diferentes de un único clúster de clústeres de conmutación por error (WSFC).</span><span class="sxs-lookup"><span data-stu-id="dd0a2-111">The server instances that host the availability replicas for a given availability group must reside on different nodes of a single Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 [<span data-ttu-id="dd0a2-112">extremo de creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="dd0a2-112">database mirroring endpoint</span></span>](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
 <span data-ttu-id="dd0a2-113">Un extremo es un objeto de SQL Server que permite la comunicación de SQL Server en la red.</span><span class="sxs-lookup"><span data-stu-id="dd0a2-113">An endpoint is a SQL Server object that enables SQL Server to communicate over the network.</span></span> <span data-ttu-id="dd0a2-114">Para participar en la creación de reflejo de la base de datos y/o [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , una instancia del servidor requiere un extremo dedicado especial.</span><span class="sxs-lookup"><span data-stu-id="dd0a2-114">To participate in database mirroring and/or [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] a server instance requires a special, dedicated endpoint.</span></span> <span data-ttu-id="dd0a2-115">Todas las conexiones de grupo de disponibilidad y creación de reflejo en una instancia de servidor utilizan el mismo extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="dd0a2-115">All mirroring and availability group connections on a server instance use the same database mirroring endpoint.</span></span> <span data-ttu-id="dd0a2-116">Se trata de un extremo especial que se utiliza exclusivamente para recibir estas conexiones procedentes de otras instancias de servidor.</span><span class="sxs-lookup"><span data-stu-id="dd0a2-116">This endpoint is a special-purpose endpoint used exclusively to receive these connections from other server instances.</span></span>  
  
##  <a name="to-configure-a-server-instance-to-support-alwayson-availability-groups"></a><a name="ConfigSI"></a><span data-ttu-id="dd0a2-117">Para configurar una instancia de servidor para admitir Grupos de disponibilidad AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="dd0a2-117">To Configure a Server Instance to Support AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="dd0a2-118">Para admitir [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], una instancia de servidor debe residir en un nodo del clúster de conmutación por error de WSFC que hospeda el grupo de disponibilidad, estar habilitada para [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] y poseer un extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="dd0a2-118">To support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], a server instance must reside on a node in the WSFC failover cluster that hosts the availability group, be [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] enabled, and possess a database mirroring endpoint.</span></span>  
  
1.  <span data-ttu-id="dd0a2-119">Habilite la característica de grupos de disponibilidad de AlwaysOn en cada instancia de servidor que vaya a participar en uno o varios grupos de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="dd0a2-119">Enable the AlwaysOn Availability Groups feature on every server instance that is to participate in one or more availability groups.</span></span> <span data-ttu-id="dd0a2-120">Una instancia del servidor determinada solo puede hospedar una única réplica de disponibilidad para un grupo de disponibilidad dado.</span><span class="sxs-lookup"><span data-stu-id="dd0a2-120">A given server instance can host only a single availability replica for a given availability group.</span></span>  
  
2.  <span data-ttu-id="dd0a2-121">Asegúrese de que la instancia del servidor posee un extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="dd0a2-121">Ensure that the server instance possesses a database mirroring endpoint.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="dd0a2-122">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="dd0a2-122">Related Tasks</span></span>  
 <span data-ttu-id="dd0a2-123">**Para habilitar los grupos de disponibilidad de AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="dd0a2-123">**To enable AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="dd0a2-124">Habilitar y deshabilitar grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dd0a2-124">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="dd0a2-125">**Para determinar si existe un extremo de creación de reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="dd0a2-125">**To determine whether a database mirroring endpoint exists**</span></span>  
  
-   [<span data-ttu-id="dd0a2-126">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dd0a2-126">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
 <span data-ttu-id="dd0a2-127">**Para crear un extremo de creación de reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="dd0a2-127">**To create a database mirroring endpoint**</span></span>  
  
-   [<span data-ttu-id="dd0a2-128">Cree un extremo de creación de reflejo de la base de datos para Grupos de disponibilidad AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="dd0a2-128">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="dd0a2-129">Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dd0a2-129">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="dd0a2-130">Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones salientes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dd0a2-130">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="dd0a2-131">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="dd0a2-131">Related Content</span></span>  
  
-   <span data-ttu-id="dd0a2-132">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="dd0a2-132">**Blogs:**</span></span>  
  
     [<span data-ttu-id="dd0a2-133">Series de aprendizaje de AlwaysON - HADRON: uso del grupo de trabajo para las bases de datos compatibles con HADRON</span><span class="sxs-lookup"><span data-stu-id="dd0a2-133">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="dd0a2-134">Blogs del equipo de AlwaysOn de SQL Server: el blog oficial del equipo de AlwaysOn de SQL Server</span><span class="sxs-lookup"><span data-stu-id="dd0a2-134">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="dd0a2-135">Blogs de los ingenieros de SQL Server de CSS</span><span class="sxs-lookup"><span data-stu-id="dd0a2-135">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="dd0a2-136">**Vídeos:**</span><span class="sxs-lookup"><span data-stu-id="dd0a2-136">**Videos:**</span></span>  
  
     [<span data-ttu-id="dd0a2-137">Microsoft SQL Server Code-Named "Denali", Serie AlwaysOn, parte 1: Introducción a la solución de alta disponibilidad de siguiente generación</span><span class="sxs-lookup"><span data-stu-id="dd0a2-137">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="dd0a2-138">Microsoft SQL Server “Denali”, Serie AlwaysOn, parte 2: Crear una solución esencial de alta disponibilidad utilizando AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="dd0a2-138">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="dd0a2-139">**Notas del producto:**</span><span class="sxs-lookup"><span data-stu-id="dd0a2-139">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="dd0a2-140">Guía de soluciones AlwaysOn de Microsoft SQL Server para lograr alta disponibilidad y recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="dd0a2-140">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="dd0a2-141">Notas del producto de Microsoft para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="dd0a2-141">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="dd0a2-142">Notas del producto del equipo de asesoramiento al cliente de SQL Server</span><span class="sxs-lookup"><span data-stu-id="dd0a2-142">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="dd0a2-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd0a2-143">See Also</span></span>  
 <span data-ttu-id="dd0a2-144">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dd0a2-144">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="dd0a2-145">[Requisitos previos, restricciones y recomendaciones para el SQL Server de &#40;de Grupos de disponibilidad AlwaysOn&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="dd0a2-145">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="dd0a2-146">[El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dd0a2-146">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="dd0a2-147">[Grupos de disponibilidad AlwaysOn: interoperabilidad (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dd0a2-147">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 <span data-ttu-id="dd0a2-148">[Clústeres de conmutación por error y &#40;de Grupos de disponibilidad AlwaysOn SQL Server&#41;](failover-clustering-and-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dd0a2-148">[Failover Clustering and AlwaysOn Availability Groups &#40;SQL Server&#41;](failover-clustering-and-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="dd0a2-149">[Clústeres de conmutación por error de Windows Server &#40;WSFC&#41; con SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dd0a2-149">[Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span></span>  
 [<span data-ttu-id="dd0a2-150">Instancias de clúster de conmutación por error de AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="dd0a2-150">AlwaysOn Failover Cluster Instances</span></span>](../../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md)  
  
