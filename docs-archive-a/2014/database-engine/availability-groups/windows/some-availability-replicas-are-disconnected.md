---
title: Algunas réplicas de disponibilidad están desconectadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp7allconnected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: aea808be-6f0f-40c2-9aa2-a2a435ec6443
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1bb6535b513770b9b4718a0e8372c0a5bc3cba84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673281"
---
# <a name="some-availability-replicas-are-disconnected"></a><span data-ttu-id="42733-102">Algunas réplicas de disponibilidad están desconectadas</span><span class="sxs-lookup"><span data-stu-id="42733-102">Some availability replicas are disconnected</span></span>
    
## <a name="introduction"></a><span data-ttu-id="42733-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="42733-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42733-104">**Nombre de directiva**</span><span class="sxs-lookup"><span data-stu-id="42733-104">**Policy Name**</span></span>|<span data-ttu-id="42733-105">Estado de conexión de las réplicas de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="42733-105">Availability Replicas Connection State</span></span>|  
|<span data-ttu-id="42733-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="42733-106">**Issue**</span></span>|<span data-ttu-id="42733-107">Algunas réplicas de disponibilidad están desconectadas.</span><span class="sxs-lookup"><span data-stu-id="42733-107">Some availability replicas are disconnected.</span></span>|  
|<span data-ttu-id="42733-108">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="42733-108">**Category**</span></span>|<span data-ttu-id="42733-109">**Warning (ADVERTENCIA)**</span><span class="sxs-lookup"><span data-stu-id="42733-109">**Warning**</span></span>|  
|<span data-ttu-id="42733-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="42733-110">**Facet**</span></span>|<span data-ttu-id="42733-111">grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="42733-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="42733-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="42733-112">Description</span></span>  
 <span data-ttu-id="42733-113">Esta directiva acumula el estado de todas las réplicas de disponibilidad y comprueba las que están en estado DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="42733-113">This policy rolls up the connection state of all availability replicas and checks for any availability replicas that are DISCONENCTED.</span></span> <span data-ttu-id="42733-114">La directiva está en mal estado cuando cualquier réplica de disponibilidad está en estado DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="42733-114">The policy is in an unhealthy state when any availability replica is DISCONNECTED.</span></span> <span data-ttu-id="42733-115">De lo contrario, la directiva está en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="42733-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42733-116"> Para esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [Algunas réplicas de disponibilidad están desconectadas](https://go.microsoft.com/fwlink/p/?LinkId=220855) en TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="42733-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas are disconnected](https://go.microsoft.com/fwlink/p/?LinkId=220855) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="42733-117">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="42733-117">Possible Causes</span></span>  
 <span data-ttu-id="42733-118">En este grupo de disponibilidad, al menos una réplica secundaria no está conectada con la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="42733-118">In this availability group, at least one secondary replica is not connected to the primary replica.</span></span> <span data-ttu-id="42733-119">El estado de conexión es DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="42733-119">The connected state is DISCONNECTED.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="42733-120">Solución posible</span><span class="sxs-lookup"><span data-stu-id="42733-120">Possible Solution</span></span>  
 <span data-ttu-id="42733-121">Use el estado de directiva de la réplica de disponibilidad para buscar la réplica de disponibilidad que está en estado DISCONNECTED y, a continuación, resuelva el problema en la réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="42733-121">Use the availability replica policy state to find the availability replica that is DISCONNECTED, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42733-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42733-122">See Also</span></span>  
 <span data-ttu-id="42733-123">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="42733-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="42733-124">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="42733-124">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
