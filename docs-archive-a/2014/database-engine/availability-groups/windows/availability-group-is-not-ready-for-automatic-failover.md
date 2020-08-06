---
title: Grupo de disponibilidad no preparado para conmutación automática por error | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp3autofailover.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 28261014-342c-442a-bd89-6d04b8d4e8b7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2995ddec51cd70d8a3f209229d0ecb9b0132c79e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663139"
---
# <a name="availability-group-is-not-ready-for-automatic-failover"></a><span data-ttu-id="edf58-102">Grupo de disponibilidad no preparado para conmutación automática por error</span><span class="sxs-lookup"><span data-stu-id="edf58-102">Availability group is not ready for automatic failover</span></span>
    
## <a name="introduction"></a><span data-ttu-id="edf58-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="edf58-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="edf58-104">**Nombre de directiva**</span><span class="sxs-lookup"><span data-stu-id="edf58-104">**Policy Name**</span></span>|<span data-ttu-id="edf58-105">Preparación para la conmutación automática por error del grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="edf58-105">Availability Group Automatic Failover Readiness</span></span>|  
|<span data-ttu-id="edf58-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="edf58-106">**Issue**</span></span>|<span data-ttu-id="edf58-107">Grupo de disponibilidad no preparado para conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="edf58-107">Availability group is not ready for automatic failover.</span></span>|  
|<span data-ttu-id="edf58-108">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="edf58-108">**Category**</span></span>|<span data-ttu-id="edf58-109">**Critical)** (Crítico)</span><span class="sxs-lookup"><span data-stu-id="edf58-109">**Critical**</span></span>|  
|<span data-ttu-id="edf58-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="edf58-110">**Facet**</span></span>|<span data-ttu-id="edf58-111">grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="edf58-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="edf58-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="edf58-112">Description</span></span>  
 <span data-ttu-id="edf58-113">Esta directiva realiza comprobaciones para asegurarse de que el grupo de disponibilidad tenga al menos una réplica secundaria que esté preparada para la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="edf58-113">This policy checks to verify that the availability group has at least one secondary replica that is failover ready.</span></span> <span data-ttu-id="edf58-114">La directiva está en mal estado y se genera una alerta cuando el modo de conmutación por error de la réplica principal es automático, pero ninguna de las réplicas secundarias del grupo de disponibilidad están listas para la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="edf58-114">The policy is in an unhealthy state and an alert is raised when the failover mode of the primary replica is automatic, however none of the secondary replicas in the availability group are failover ready.</span></span>  
  
 <span data-ttu-id="edf58-115">La directiva está en un estado correcto cuando al menos una réplica secundaria está lista para la conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="edf58-115">The policy is in a healthy state when at least one secondary replica is automatic failover ready.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="edf58-116">En esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [El grupo de disponibilidad no está listo para la conmutación automática por error](https://go.microsoft.com/fwlink/p/?LinkId=220851) en TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="edf58-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability group is not ready for automatic failover](https://go.microsoft.com/fwlink/p/?LinkId=220851) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="edf58-117">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="edf58-117">Possible Causes</span></span>  
 <span data-ttu-id="edf58-118">Grupo de disponibilidad no preparado para la conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="edf58-118">The availability group is not ready for automatic failover.</span></span> <span data-ttu-id="edf58-119">La réplica principal está configurada para la conmutación automática por error; sin embargo, la réplica secundaria no está lista para la conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="edf58-119">The primary replica is configured for automatic failover; however, the secondary replica is not ready for automatic failover.</span></span> <span data-ttu-id="edf58-120">La réplica secundaria configurada para la conmutación automática por error podría no estar disponible o su estado de sincronización de datos no es actualmente SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="edf58-120">The secondary replica that is configured for automatic failover might be unavailable or its data synchronization state is currently not SYNCHRONIZED.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="edf58-121">Soluciones posibles</span><span class="sxs-lookup"><span data-stu-id="edf58-121">Possible Solutions</span></span>  
 <span data-ttu-id="edf58-122">Las siguientes son posibles soluciones para este problema:</span><span class="sxs-lookup"><span data-stu-id="edf58-122">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="edf58-123">Compruebe que al menos una réplica secundaria está configurada como conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="edf58-123">Verify that at least one secondary replica is configured as automatic failover.</span></span> <span data-ttu-id="edf58-124">Si no hay una réplica secundaria configurada como conmutación automática por error, actualice la configuración de una réplica secundaria para que sea el destino de la conmutación automática por error con confirmación sincrónica.</span><span class="sxs-lookup"><span data-stu-id="edf58-124">If there is not a secondary replica configured as automatic failover, update the configuration of a secondary replica to be the automatic failover target with synchronous commit.</span></span>  
  
-   <span data-ttu-id="edf58-125">Use la directiva para comprobar que los datos están en un estado de sincronización y el destino de la conmutación automática por error es SYNCHRONIZED y, a continuación, resuelva el problema en la réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="edf58-125">Use the policy to verify that the data is in a synchronization state and the automatic failover target is SYNCHRONIZED, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edf58-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="edf58-126">See Also</span></span>  
 <span data-ttu-id="edf58-127">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="edf58-127">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="edf58-128">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="edf58-128">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
