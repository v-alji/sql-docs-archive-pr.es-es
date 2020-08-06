---
title: El servicio de clúster WSFC está sin conexión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp1WSFCquorum.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: d502548d-ece6-4a42-9ded-2157d33e3d21
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6e7b48f96eb09638291b1d0655d385d606b1666
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746530"
---
# <a name="wsfc-cluster-service-is-offline"></a><span data-ttu-id="afb90-102">El servicio de clúster de WSFC está sin conexión</span><span class="sxs-lookup"><span data-stu-id="afb90-102">WSFC cluster service is offline</span></span>
    
## <a name="introduction"></a><span data-ttu-id="afb90-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="afb90-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="afb90-104">**Nombre de directiva**</span><span class="sxs-lookup"><span data-stu-id="afb90-104">**Policy Name**</span></span>|<span data-ttu-id="afb90-105">Estado de clúster de WSFC</span><span class="sxs-lookup"><span data-stu-id="afb90-105">WSFC Cluster State</span></span>|  
|<span data-ttu-id="afb90-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="afb90-106">**Issue**</span></span>|<span data-ttu-id="afb90-107">El servicio de clúster de WSFC está sin conexión.</span><span class="sxs-lookup"><span data-stu-id="afb90-107">WSFC cluster service is offline.</span></span>|  
|<span data-ttu-id="afb90-108">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="afb90-108">**Category**</span></span>|<span data-ttu-id="afb90-109">**Critical)** (Crítico)</span><span class="sxs-lookup"><span data-stu-id="afb90-109">**Critical**</span></span>|  
|<span data-ttu-id="afb90-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="afb90-110">**Facet**</span></span>|<span data-ttu-id="afb90-111">Instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="afb90-111">Instance of SQL Server</span></span>|  
  
## <a name="description"></a><span data-ttu-id="afb90-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="afb90-112">Description</span></span>  
 <span data-ttu-id="afb90-113">Esta directiva comprueba el estado del clúster de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="afb90-113">This policy checks the state of the Windows Server Failover Cluster (WSFC).</span></span> <span data-ttu-id="afb90-114">La directiva está en mal estado y se genera una alerta cuando el clúster de WSFC está sin conexión o en el estado de quorum forzado.</span><span class="sxs-lookup"><span data-stu-id="afb90-114">The policy is in an unhealthy state and an alert is raised when the WSFC cluster is offline or in the forced quorum state.</span></span> <span data-ttu-id="afb90-115">Todos los grupos de disponibilidad hospedados en este clúster están sin conexión o se requiere una acción de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="afb90-115">All availability groups hosted within this cluster are offline or a disaster recovery action is required.</span></span>  
  
 <span data-ttu-id="afb90-116">El estado de la directiva es correcto cuando el estado del clúster está en el quorum normal.</span><span class="sxs-lookup"><span data-stu-id="afb90-116">The policy state is healthy when the cluster state is in the normal quorum.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="afb90-117">Para esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [El servicio de clúster de WSFC está desconectado](https://go.microsoft.com/fwlink/p/?LinkId=220849) en TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="afb90-117">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [WSFC cluster service is offline](https://go.microsoft.com/fwlink/p/?LinkId=220849) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="afb90-118">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="afb90-118">Possible Causes</span></span>  
 <span data-ttu-id="afb90-119">Esto puede deberse a un problema del servicio de clúster o a la pérdida del quorum en el clúster.</span><span class="sxs-lookup"><span data-stu-id="afb90-119">This issue can be caused by a cluster service issue or by the loss of the quorum in the cluster.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="afb90-120">Solución posible</span><span class="sxs-lookup"><span data-stu-id="afb90-120">Possible Solution</span></span>  
 <span data-ttu-id="afb90-121">Use la herramienta Administrador de clústeres para realizar el flujo de trabajo de quorum forzado o de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="afb90-121">Use the Cluster Administrator tool to perform the forced quorum or disaster recovery workflow.</span></span> <span data-ttu-id="afb90-122">Si no puede resolver el problema al realizar el quorum forzado o la recuperación ante desastres, póngase en contacto con el administrador de clústeres para que le ayude a solucionar este problema.</span><span class="sxs-lookup"><span data-stu-id="afb90-122">If you cannot resolve the issue by performing the forced quorum or disaster recovery, contact your cluster administrator to help resolve this issue.</span></span> <span data-ttu-id="afb90-123">Para obtener más información, vea [Forzar el inicio de un clúster WSFC sin un cuórum](../../../sql-server/failover-clusters/windows/force-a-wsfc-cluster-to-start-without-a-quorum.md) en los Libros en línea de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="afb90-123">For more information, see [Force a WSFC Cluster to Start Without a Quorum](../../../sql-server/failover-clusters/windows/force-a-wsfc-cluster-to-start-without-a-quorum.md) in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb90-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="afb90-124">See Also</span></span>  
 <span data-ttu-id="afb90-125">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="afb90-125">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="afb90-126">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="afb90-126">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
