---
title: La réplica de disponibilidad no está unida | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp4joined.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 9c0d10b1-9e12-430c-83b9-ca2bd0a3afc4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7c4f76e98d373e50124f5ca2b135a9fad8f34226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746534"
---
# <a name="availability-replica-is-not-joined"></a><span data-ttu-id="8ebdb-102">La réplica de disponibilidad no está unida</span><span class="sxs-lookup"><span data-stu-id="8ebdb-102">Availability replica is not joined</span></span>
    
## <a name="introduction"></a><span data-ttu-id="8ebdb-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="8ebdb-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8ebdb-104">**Nombre de directiva**</span><span class="sxs-lookup"><span data-stu-id="8ebdb-104">**Policy Name**</span></span>|<span data-ttu-id="8ebdb-105">Estado de unión de réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="8ebdb-105">Availability Replica Join State</span></span>|  
|<span data-ttu-id="8ebdb-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8ebdb-106">**Issue**</span></span>|<span data-ttu-id="8ebdb-107">La réplica de disponibilidad no está unida.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-107">Availability Replica is not joined.</span></span>|  
|<span data-ttu-id="8ebdb-108">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="8ebdb-108">**Category**</span></span>|<span data-ttu-id="8ebdb-109">**Warning (ADVERTENCIA)**</span><span class="sxs-lookup"><span data-stu-id="8ebdb-109">**Warning**</span></span>|  
|<span data-ttu-id="8ebdb-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="8ebdb-110">**Facet**</span></span>|<span data-ttu-id="8ebdb-111">réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="8ebdb-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8ebdb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ebdb-112">Description</span></span>  
 <span data-ttu-id="8ebdb-113">Esta directiva comprueba el estado de unión de la réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-113">This policy checks the join state of the availability replica.</span></span> <span data-ttu-id="8ebdb-114">La directiva está en mal estado cuando la réplica de disponibilidad se agrega al grupo de disponibilidad, pero no se une correctamente.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-114">The policy is in an unhealthy state when the availability replica is added to the availability group, but is not joined properly.</span></span> <span data-ttu-id="8ebdb-115">De lo contrario, la directiva está en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8ebdb-116">Para esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [La réplica de disponibilidad no está unida](https://go.microsoft.com/fwlink/p/?LinkId=220859) en TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica is not joined](https://go.microsoft.com/fwlink/p/?LinkId=220859) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="8ebdb-117">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="8ebdb-117">Possible Causes</span></span>  
 <span data-ttu-id="8ebdb-118">La réplica secundaria no se ha unido al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-118">The secondary replica is not joined to the availability group.</span></span> <span data-ttu-id="8ebdb-119">Para que una réplica de disponibilidad se una correctamente al grupo de disponibilidad, el estado de la unión debe ser Instancia independiente unida (1) o Clúster de conmutación por error unido (2).</span><span class="sxs-lookup"><span data-stu-id="8ebdb-119">For an availability replica to be successfully joined to the availability group, the join state must be Joined Standalone Instance (1) or Joined Failover Cluster (2).</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="8ebdb-120">Solución posible</span><span class="sxs-lookup"><span data-stu-id="8ebdb-120">Possible Solution</span></span>  
 <span data-ttu-id="8ebdb-121">Use Transact-SQL, PowerShell o SQL Server Management Studio para combinar la réplica secundaria con el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-121">Use Transact-SQL, PowerShell, or SQL Server Management Studio to join the secondary replica to the availability group.</span></span> <span data-ttu-id="8ebdb-122">Para obtener más información sobre cómo combinar las réplicas secundarias con los grupos de disponibilidad, vea [Combinar una réplica secundaria con un grupo de disponibilidad (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="8ebdb-122">For more information about joining secondary replicas to availability groups, see [Joining a Secondary Replica to an Availability Group (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ebdb-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ebdb-123">See Also</span></span>  
 <span data-ttu-id="8ebdb-124">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8ebdb-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="8ebdb-125">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8ebdb-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
