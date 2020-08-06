---
title: Grupo de disponibilidad sin conexión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp2online.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 093c5208-bf7a-49f4-a546-72b48197cadf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b25e5b22a09783c8dfcad862500b5c0dfcb2c319
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663136"
---
# <a name="availability-group-is-offline"></a><span data-ttu-id="dc78d-102">Grupo de disponibilidad sin conexión</span><span class="sxs-lookup"><span data-stu-id="dc78d-102">Availability group is offline</span></span>
    
## <a name="introduction"></a><span data-ttu-id="dc78d-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="dc78d-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dc78d-104">**Nombre de directiva**</span><span class="sxs-lookup"><span data-stu-id="dc78d-104">**Policy Name**</span></span>|<span data-ttu-id="dc78d-105">Estado en línea del grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="dc78d-105">Availability Group Online State</span></span>|  
|<span data-ttu-id="dc78d-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="dc78d-106">**Issue**</span></span>|<span data-ttu-id="dc78d-107">El grupo de disponibilidad está sin conexión.</span><span class="sxs-lookup"><span data-stu-id="dc78d-107">Availability group is offline.</span></span>|  
|<span data-ttu-id="dc78d-108">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="dc78d-108">**Category**</span></span>|<span data-ttu-id="dc78d-109">**Critical)** (Crítico)</span><span class="sxs-lookup"><span data-stu-id="dc78d-109">**Critical**</span></span>|  
|<span data-ttu-id="dc78d-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="dc78d-110">**Facet**</span></span>|<span data-ttu-id="dc78d-111">grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="dc78d-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dc78d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc78d-112">Description</span></span>  
 <span data-ttu-id="dc78d-113">Esta directiva comprueba el estado en línea o sin conexión del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="dc78d-113">This policy checks the online or offline state of the availability group.</span></span> <span data-ttu-id="dc78d-114">La directiva está en mal estado y se genera una alerta cuando el recurso de clúster del grupo de disponibilidad está sin conexión o no tiene una réplica principal.</span><span class="sxs-lookup"><span data-stu-id="dc78d-114">The policy is in an unhealthy state and an alert is raised when the cluster resource of the availability group is offline or the availability group does not have a primary replica.</span></span>  
  
 <span data-ttu-id="dc78d-115">El estado de la directiva es correcto cuando el recurso de clúster del grupo de disponibilidad está en línea y el grupo de disponibilidad tiene una réplica principal.</span><span class="sxs-lookup"><span data-stu-id="dc78d-115">The policy state is healthy when the cluster resource of the availability group is online and the availability group has a primary replica.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc78d-116"> Para esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [El grupo de disponibilidad está desconectado](https://go.microsoft.com/fwlink/p/?LinkId=220850) en TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="dc78d-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability group is offline](https://go.microsoft.com/fwlink/p/?LinkId=220850) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="dc78d-117">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="dc78d-117">Possible Causes</span></span>  
 <span data-ttu-id="dc78d-118">Este problema se puede deber a un error en la instancia del servidor que hospeda la réplica principal o a que el recurso de grupo de disponibilidad del clúster de conmutación por error de Windows Server (WSFC) se ha quedado sin conexión.</span><span class="sxs-lookup"><span data-stu-id="dc78d-118">This issue can be caused by a failure in the server instance that hosts the primary replica or by the Windows Server Failover Cluster (WSFC) availability group resource going offline.</span></span> <span data-ttu-id="dc78d-119">A continuación se indican las posibles causas de que el grupo de disponibilidad esté sin conexión:</span><span class="sxs-lookup"><span data-stu-id="dc78d-119">Following are possible causes for the availability group to be offline:</span></span>  
  
-   <span data-ttu-id="dc78d-120">El grupo de disponibilidad no está configurado con el modo de conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="dc78d-120">The availability group is not configured with automatic failover mode.</span></span> <span data-ttu-id="dc78d-121">La réplica principal deja de estar disponible y el rol de todas las réplicas del grupo de disponibilidad es RESUELVE AFTER.</span><span class="sxs-lookup"><span data-stu-id="dc78d-121">The primary replica becomes unavailable and the role of all replicas in the availability group become RESOLVING.</span></span>  
  
    -   <span data-ttu-id="dc78d-122">El servicio de instancia de la réplica principal está inactivo o no responde.</span><span class="sxs-lookup"><span data-stu-id="dc78d-122">The primary replica instance service is down or unresponsive.</span></span>  
  
    -   <span data-ttu-id="dc78d-123">El grupo de disponibilidad tiene un problema de conectividad con el clúster.</span><span class="sxs-lookup"><span data-stu-id="dc78d-123">The availability group has a connectivity issue with the cluster.</span></span>  
  
-   <span data-ttu-id="dc78d-124">El grupo de disponibilidad está configurado con el modo de conmutación automática por error y no se completa correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc78d-124">The availability group is configured with automatic failover mode and does not complete successfully.</span></span>  
  
    -   <span data-ttu-id="dc78d-125">Durante la conmutación automática por error, se produce un error en la comprobación de preparación principal en la réplica de destino, y no hay ninguna réplica disponible para convertirse en la nueva réplica principal.</span><span class="sxs-lookup"><span data-stu-id="dc78d-125">During the automatic failover, the primary readiness check on the target replica fails, and there is no replica available to become the new primary.</span></span>  
  
-   <span data-ttu-id="dc78d-126">El recurso de grupo de disponibilidad del clúster se queda sin conexión.</span><span class="sxs-lookup"><span data-stu-id="dc78d-126">The availability group resource in the cluster becomes offline.</span></span>  
  
    -   <span data-ttu-id="dc78d-127">Cualquier recurso de clúster dependiente encuentra un problema crítico y se queda sin conexión.</span><span class="sxs-lookup"><span data-stu-id="dc78d-127">Any dependent cluster resource encounters a critical issue and becomes offline.</span></span> <span data-ttu-id="dc78d-128">El recurso de grupo de disponibilidad también está sin conexión hasta que el recurso dependiente vuelve a estar en línea.</span><span class="sxs-lookup"><span data-stu-id="dc78d-128">The availability group resource is also offline until the dependent resource becomes online.</span></span>  
  
    -   <span data-ttu-id="dc78d-129">Un problema crítico en el clúster desactiva el recurso de grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="dc78d-129">A critical issue in the cluster turns off the availability group resource.</span></span>  
  
-   <span data-ttu-id="dc78d-130">Hay una conmutación por error automática, manual o forzada en curso para el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="dc78d-130">There is an automatic, manual, or forced failover in progress for the availability group.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="dc78d-131">Soluciones posibles</span><span class="sxs-lookup"><span data-stu-id="dc78d-131">Possible Solutions</span></span>  
 <span data-ttu-id="dc78d-132">Las siguientes son posibles soluciones para este problema:</span><span class="sxs-lookup"><span data-stu-id="dc78d-132">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="dc78d-133">Si la instancia de SQL Server de la réplica principal está inactiva, reinicie el servidor y compruebe que el grupo de disponibilidad se recupera en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="dc78d-133">If the SQL Server instance of the primary replica is down, restart the server and then verify that the availability group recovers to a healthy state.</span></span>  
  
-   <span data-ttu-id="dc78d-134">Si parece que se ha producido un error en la conmutación automática por error, compruebe que las bases de datos de la réplica están sincronizadas con la réplica principal conocida y, a continuación, conmute por error a la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="dc78d-134">If the automatic failover appears to have failed, verify that the databases on the replica are synchronized with the previously known primary replica, and then failover to the primary replica.</span></span> <span data-ttu-id="dc78d-135">Si las bases de datos no están sincronizadas, seleccione una réplica con una pérdida de datos mínima y, a continuación, recupere el modo de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="dc78d-135">If the databases are not synchronized, select a replica with a minimum loss of data, and then recover to failover mode.</span></span>  
  
-   <span data-ttu-id="dc78d-136">Si el recurso del clúster está sin conexión mientras que las instancias de SQL Server parecen estar en buen estado, use el Administrador de clústeres de conmutación por error para comprobar el estado del clúster u otros problemas de clúster en el servidor.</span><span class="sxs-lookup"><span data-stu-id="dc78d-136">If the resource in the cluster is offline while the instances of SQL Server appear to be healthy, use Failover Cluster Manager to check the cluster health or other cluster issues on the server.</span></span> <span data-ttu-id="dc78d-137">También puede usar el Administrador de clústeres de conmutación por error para intentar poner en línea el recurso de grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="dc78d-137">You can also use the Failover Cluster Manager to attempt to turn the availability group resource online.</span></span>  
  
-   <span data-ttu-id="dc78d-138">Si hay una conmutación por error en curso, espere a que se complete.</span><span class="sxs-lookup"><span data-stu-id="dc78d-138">If there is a failover in progress, wait for the failover to complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc78d-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc78d-139">See Also</span></span>  
 <span data-ttu-id="dc78d-140">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dc78d-140">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="dc78d-141">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="dc78d-141">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
