---
title: 'Creación de reflejo de la base de datos: interoperabilidad y coexistencia (SQL Server) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- high availability [SQL Server], interoperability and coexistence
- Database Engine [SQL Server], high availability
ms.assetid: 89fef397-e0cf-4e08-b598-25b8d4170523
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 057392842974c3342fc57d0ec113f8b1bb58b9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671683"
---
# <a name="database-mirroring-interoperability-and-coexistence-sql-server"></a><span data-ttu-id="d1466-102">Creación de reflejo de la base de datos: interoperabilidad y coexistencia (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d1466-102">Database Mirroring: Interoperability and Coexistence (SQL Server)</span></span>
  <span data-ttu-id="d1466-103">La creación de reflejo de la base de datos se puede utilizar con las siguientes características o componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d1466-103">Database mirroring can be used with the following features or components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [<span data-ttu-id="d1466-104">Instancias de clúster de conmutación por error de AlwaysOn (clústeres de conmutación por error de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d1466-104">AlwaysOn Failover Cluster Instances (SQL Server Failover Clustering)</span></span>](database-mirroring-and-sql-server-failover-cluster-instances.md)  
  
-   [<span data-ttu-id="d1466-105">Captura de datos modificados (y seguimiento de cambios)</span><span class="sxs-lookup"><span data-stu-id="d1466-105">Change data capture (and change tracking)</span></span>](../../relational-databases/track-changes/change-data-capture-and-other-sql-server-features.md)  
  
-   [<span data-ttu-id="d1466-106">Instantáneas de base de datos</span><span class="sxs-lookup"><span data-stu-id="d1466-106">Database snapshots</span></span>](../../relational-databases/databases/database-snapshots-sql-server.md)  
  
-   [<span data-ttu-id="d1466-107">Catálogos de texto completo</span><span class="sxs-lookup"><span data-stu-id="d1466-107">Full-text catalogs</span></span>](database-mirroring-and-full-text-catalogs-sql-server.md)  
  
-   [<span data-ttu-id="d1466-108">Trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="d1466-108">Log shipping</span></span>](database-mirroring-and-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="d1466-109">Replicación</span><span class="sxs-lookup"><span data-stu-id="d1466-109">Replication</span></span>](database-mirroring-and-replication-sql-server.md)  
  
 <span data-ttu-id="d1466-110">La creación de reflejo de la base de datos no interopera con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d1466-110">Database mirroring does not interoperate with the following:</span></span>  
  
-   <span data-ttu-id="d1466-111">Transacciones entre bases de datos y transacciones distribuidas</span><span class="sxs-lookup"><span data-stu-id="d1466-111">Cross-database transactions/distributed transactions</span></span>  
  
     <span data-ttu-id="d1466-112">Si quiere saber por qué no se admiten estas transacciones, vea [Transacciones entre bases de datos no compatibles para la creación de reflejo de la base de datos o grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](../availability-groups/windows/transactions-always-on-availability-and-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="d1466-112">For information about why such transactions are not supported, see [Cross-Database Transactions Not Supported For Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;](../availability-groups/windows/transactions-always-on-availability-and-database-mirroring.md).</span></span>  
  
-   [!INCLUDE[ssHADR](../../includes/sshadr-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d1466-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1466-113">See Also</span></span>  
 [<span data-ttu-id="d1466-114">Creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d1466-114">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
