---
title: Instantáneas de base de datos con Grupos de disponibilidad AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 7432da1c-ce2f-4cd9-af41-54c97744166b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1e4307653b5b8150d71019a373ee073d15123f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748261"
---
# <a name="database-snapshots-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="8cc7e-102">Instantáneas de bases de datos con grupos de disponibilidad AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8cc7e-102">Database Snapshots with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="8cc7e-103">Puede crear una instantánea de base de datos en una base de datos primaria o secundaria en un grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="8cc7e-103">You can create a database snapshot on an primary or secondary database in an availability group.</span></span> <span data-ttu-id="8cc7e-104">El rol de réplica debe ser PRIMARY o SECONDARY y no debe encontrarse en el estado RESOLVING.</span><span class="sxs-lookup"><span data-stu-id="8cc7e-104">The replica role must be either PRIMARY or SECONDARY, not in the RESOLVING state.</span></span>  
  
 <span data-ttu-id="8cc7e-105">Se recomienda que el estado de sincronización de la base de datos sea SYNCHRONIZING o SYNCHRONIZED cuando se crea una instantánea de base de datos.</span><span class="sxs-lookup"><span data-stu-id="8cc7e-105">We recommend that the database synchronization state be SYNCHRONIZING or SYNCHRONIZED when you create a database snapshot.</span></span> <span data-ttu-id="8cc7e-106">Sin embargo, las instantáneas de base de datos pueden crearse cuando el estado de sincronización de la base de datos sea NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="8cc7e-106">However, database snapshots can be created when the database synchronization state is NOT SYNCHRONIZING.</span></span>  
  
 <span data-ttu-id="8cc7e-107">Una instantánea de base de datos debe seguir funcionando aunque la réplica se DESCONECTE de la réplica primaria.</span><span class="sxs-lookup"><span data-stu-id="8cc7e-107">A database snapshot on a secondary replica should continue to work if the replica is DISCONNECTED from the primary replica.</span></span>  
  
 <span data-ttu-id="8cc7e-108">Algunas condiciones de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] pueden hacer que la base de datos de origen y sus instantáneas de base de datos se reinicien y desconecten temporalmente a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8cc7e-108">Some [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] conditions cause both the source database and its database snapshots to be restarted, temporarily disconnecting users.</span></span> <span data-ttu-id="8cc7e-109">Estas condiciones son:</span><span class="sxs-lookup"><span data-stu-id="8cc7e-109">These conditions are as follows:</span></span>  
  
-   <span data-ttu-id="8cc7e-110">La réplica principal cambia los roles, ya sea porque la réplica principal actual se queda sin conexión y vuelve a conectarse en la misma instancia del servidor o porque se produce un error en el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="8cc7e-110">The primary replica changes roles, whether because the current primary replica goes off line and comes back online on the same server instance or because the availability group fails over.</span></span>  
  
-   <span data-ttu-id="8cc7e-111">La base de datos entra en el rol secundario.</span><span class="sxs-lookup"><span data-stu-id="8cc7e-111">The database enters the secondary role.</span></span>  
  
 <span data-ttu-id="8cc7e-112">Si se produce una conmutación por error de la réplica de disponibilidad que hospeda las instantáneas de base de datos, estas permanecen en la instancia del servidor donde se crearon.</span><span class="sxs-lookup"><span data-stu-id="8cc7e-112">If the availability replica that hosts database snapshots is failed over, the database snapshots remain on the server instance where they were created.</span></span> <span data-ttu-id="8cc7e-113">Los usuarios pueden seguir usando las instantáneas tras la conmutación por error. Si el rendimiento es importante en el entorno, se recomienda crear instantáneas de base de datos solo en las bases de datos secundarias que estén hospedadas por una réplica secundaria configurada para el modo de conmutación por error manual.</span><span class="sxs-lookup"><span data-stu-id="8cc7e-113">Users can continue to use the snapshots after the failover.If performance is a concern in your environment, we recommend that you create database snapshots only on secondary databases that are hosted by a secondary replica that is configured for manual failover mode.</span></span>  <span data-ttu-id="8cc7e-114">Si alguna vez realiza una conmutación por error manual del grupo de disponibilidad en esta réplica secundaria, puede crear un conjunto de instantáneas de base de datos en otra réplica secundaria, redirigir a los clientes a las nuevas instantáneas de base de datos y quitar todas las instantáneas de las bases de datos principales.</span><span class="sxs-lookup"><span data-stu-id="8cc7e-114">If you ever manually fail over the availability group to this secondary replica, you can create a new set of database snapshots on another secondary replica, redirect clients to the new database snapshots, and drop all of the database snapshots from the now primary databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cc7e-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8cc7e-115">See Also</span></span>  
 <span data-ttu-id="8cc7e-116">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8cc7e-116">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="8cc7e-117">Instantáneas de bases de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8cc7e-117">Database Snapshots &#40;SQL Server&#41;</span></span>](../../../relational-databases/databases/database-snapshots-sql-server.md)  
  
  
