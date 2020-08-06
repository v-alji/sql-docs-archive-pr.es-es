---
title: Compatibilidad con alta disponibilidad para bases de datos OLTP en memoria | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 2113a916-3b1e-496c-8650-7f495e492510
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 092f2b8158bb35286a09103ea645b2aeb1374fc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748793"
---
# <a name="high-availability-support-for-in-memory-oltp-databases"></a><span data-ttu-id="7288e-102">Compatibilidad con alta disponibilidad para bases de datos OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="7288e-102">High Availability Support for In-Memory OLTP databases</span></span>
  <span data-ttu-id="7288e-103">Las bases de datos que contienen tablas optimizadas para memoria, con o sin procedimientos almacenados compilados nativos, son totalmente compatibles con grupos de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="7288e-103">Databases containing memory-optimized tables, with or without native compiled stored procedures, are fully supported with AlwaysOn Availability Groups.</span></span>  <span data-ttu-id="7288e-104">No hay ninguna diferencia en la configuración y la compatibilidad de las bases de datos que contienen objetos de [!INCLUDE[hek_2](../../includes/hek-2-md.md)] en comparación con las que no tienen.</span><span class="sxs-lookup"><span data-stu-id="7288e-104">There is no difference in the configuration and support for databases which contain [!INCLUDE[hek_2](../../includes/hek-2-md.md)] objects as compared to those without,</span></span>  
  
## <a name="alwayson-availability-groups-and-in-memory-oltp-databases"></a><span data-ttu-id="7288e-105">Grupos de disponibilidad AlwaysOn y bases de datos OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="7288e-105">AlwaysOn Availability Groups and In-Memory OLTP Databases</span></span>  
 <span data-ttu-id="7288e-106">La configuración de bases de datos con componentes de [!INCLUDE[hek_2](../../includes/hek-2-md.md)] proporciona lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7288e-106">Configuring databases with [!INCLUDE[hek_2](../../includes/hek-2-md.md)] components provides the following:</span></span>  
  
-   <span data-ttu-id="7288e-107">**Una experiencia completamente integrada** </span><span class="sxs-lookup"><span data-stu-id="7288e-107">**A fully integrated experience** </span></span>  
    <span data-ttu-id="7288e-108">Puede configurar las bases de datos que contienen tablas optimizadas para memoria usando el mismo asistente con el mismo nivel de compatibilidad para las réplicas secundarias sincrónicas y asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="7288e-108">You can configure your databases containing memory-optimized tables using the same wizard with the same level of support for both synchronous and asynchronous secondary replicas.</span></span> <span data-ttu-id="7288e-109">Además, el seguimiento de estado se proporciona con el panel AlwaysOn familiar en SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="7288e-109">Additionally, health monitoring is provided using the familiar AlwaysOn dashboard in SQL Server Management Studio.</span></span>  
  
-   <span data-ttu-id="7288e-110">**Tiempo de conmutación por error comparable** </span><span class="sxs-lookup"><span data-stu-id="7288e-110">**Comparable Failover time** </span></span>  
    <span data-ttu-id="7288e-111">Las réplicas secundarias mantienen el estado en memoria de las tablas duraderas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="7288e-111">Secondary replicas maintain the in-memory state of the durable memory-optimized tables.</span></span> <span data-ttu-id="7288e-112">En caso de conmutación por error automática o forzada, el tiempo de conmutación por error a la nueva principal es comparable a las tablas de bases de disco ya que no es necesaria la recuperación.</span><span class="sxs-lookup"><span data-stu-id="7288e-112">In the event of automatic or forced failover, the time to failover to the new primary is comparable to disk-bases tables as no recovery is needed.</span></span> <span data-ttu-id="7288e-113">En esta configuración, se admiten tablas con optimización para memoria creadas como SCHEMA_ONLY.</span><span class="sxs-lookup"><span data-stu-id="7288e-113">Memory-optimized tables created as SCHEMA_ONLY are supported in this configuration.</span></span> <span data-ttu-id="7288e-114">Sin embargo, no se registran los cambios en estas tablas y, por tanto, no existirá ningún dato en estas tablas en la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="7288e-114">However changes to these tables are not logged and therefore no data will exist in these tables on the secondary replica.</span></span>  
  
-   <span data-ttu-id="7288e-115">**Secundario legible** </span><span class="sxs-lookup"><span data-stu-id="7288e-115">**Readable Secondary** </span></span>  
    <span data-ttu-id="7288e-116">Puede obtener acceso a las tablas optimizadas para memoria en la réplica secundaria y consultarlas si se ha configurado para acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="7288e-116">You can access and query memory-optimized tables on the secondary replica if it has been configured for read access.</span></span> <span data-ttu-id="7288e-117">Para más información, vea [Secundarias activas: réplicas secundarias legibles (grupos de disponibilidad AlwaysOn)](../../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="7288e-117">For more information see [Active Secondaries: Readable Secondary Replicas (AlwaysOn Availability Groups)](../../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
## <a name="failover-clustering-instance-fci-and-in-memory-oltp-databases"></a><span data-ttu-id="7288e-118">Instancia de clústeres de conmutación por error (FCI) y bases de datos OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="7288e-118">Failover Clustering Instance (FCI) and In-Memory OLTP Databases</span></span>  
 <span data-ttu-id="7288e-119">Para lograr alta disponibilidad en una configuración de almacenamiento compartido, puede configurar clústeres de conmutación por error en instancias con una o varias bases de datos optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="7288e-119">To achieve high-availability in a shared-storage configuration, you can setup failover clustering on instances with one or more database with memory-optimized tables.</span></span> <span data-ttu-id="7288e-120">Necesitará tener en cuenta los siguientes factores como parte de la configuración de una FCI.</span><span class="sxs-lookup"><span data-stu-id="7288e-120">You need to consider the following factors as part of setting up an FCI.</span></span>  
  
-   <span data-ttu-id="7288e-121">**Objetivo de tiempo de recuperación** </span><span class="sxs-lookup"><span data-stu-id="7288e-121">**Recovery Time Objective** </span></span>  
    <span data-ttu-id="7288e-122">El tiempo de conmutación por error será mayor ya que las tablas optimizadas para memoria deben cargarse en memoria antes de que la base de datos pueda estar disponible.</span><span class="sxs-lookup"><span data-stu-id="7288e-122">Failover time will likely to be higher as the memory-optimized tables must be loaded into memory before the database is made available.</span></span>  
  
-   <span data-ttu-id="7288e-123">**Tablas SCHEMA_ONLY** </span><span class="sxs-lookup"><span data-stu-id="7288e-123">**SCHEMA_ONLY tables** </span></span>  
    <span data-ttu-id="7288e-124">Tenga en cuenta que las tablas SCHEMA_ONLY estarán vacías sin filas después de la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="7288e-124">Be aware that SCHEMA_ONLY tables will be empty with no rows after the failover.</span></span> <span data-ttu-id="7288e-125">Así es como se ha diseñado y definido por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7288e-125">This is as designed and defined by the application.</span></span> <span data-ttu-id="7288e-126">Este es exactamente el mismo comportamiento que cuando se reinicia una base de datos [!INCLUDE[hek_2](../../includes/hek-2-md.md)] con una o más tablas SCHEMA_ONLY.</span><span class="sxs-lookup"><span data-stu-id="7288e-126">This is exactly the same behavior when you restart an [!INCLUDE[hek_2](../../includes/hek-2-md.md)] database with one or more SCHEMA_ONLY tables.</span></span>  
  
## <a name="support-for-transaction-replication-in-in-memory-oltp"></a><span data-ttu-id="7288e-127">Compatibilidad para la replicación de transacciones en OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="7288e-127">Support for transaction replication in In-Memory OLTP</span></span>  
 <span data-ttu-id="7288e-128">Las tablas que actúan como suscriptores de replicación transaccional, excluida la replicación transaccional punto a punto, pueden configurarse como tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="7288e-128">Tables acting as transactional replication subscribers, excluding Peer-to-peer transactional replication, can be configured as memory-optimized tables.</span></span> <span data-ttu-id="7288e-129">Otras configuraciones de replicación no son compatibles con las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="7288e-129">Other replication configurations are not compatible with memory-optimized tables.</span></span>  <span data-ttu-id="7288e-130">Para obtener más información, vea [Replicación en suscriptores de tablas con optimización para memoria](../replication/replication-to-memory-optimized-table-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="7288e-130">For more information see [Replication to Memory-Optimized Table Subscribers](../replication/replication-to-memory-optimized-table-subscribers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7288e-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7288e-131">See Also</span></span>  
 <span data-ttu-id="7288e-132">[Grupos de disponibilidad AlwaysOn (SQL Server)](../../database-engine/availability-groups/windows/always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7288e-132">[AlwaysOn Availability Groups (SQL Server)](../../database-engine/availability-groups/windows/always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="7288e-133">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7288e-133">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="7288e-134">[Secundarias activas: réplicas secundarias legibles &#40;Grupos de disponibilidad AlwaysOn&#41;](../../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="7288e-134">[Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;](../../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="7288e-135">Replicación en suscriptores de tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="7288e-135">Replication to Memory-Optimized Table Subscribers</span></span>](../replication/replication-to-memory-optimized-table-subscribers.md)  
  
  