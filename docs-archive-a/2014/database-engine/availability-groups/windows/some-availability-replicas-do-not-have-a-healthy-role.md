---
title: Algunas réplicas de disponibilidad no tienen un rol en buen estado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp6allroleshealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 7ec5b337-7201-4a66-a541-7560f8b18784
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 801fe20edf6f2dbe09bc800722cf4210988ebc69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673277"
---
# <a name="some-availability-replicas-do-not-have-a-healthy-role"></a><span data-ttu-id="43ec6-102">Algunas réplicas de disponibilidad no tienen un rol en buen estado</span><span class="sxs-lookup"><span data-stu-id="43ec6-102">Some availability replicas do not have a healthy role</span></span>
    
## <a name="introduction"></a><span data-ttu-id="43ec6-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="43ec6-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="43ec6-104">**Nombre de directiva**</span><span class="sxs-lookup"><span data-stu-id="43ec6-104">**Policy Name**</span></span>|<span data-ttu-id="43ec6-105">Estado del rol de réplicas de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="43ec6-105">Availability Replicas Role State</span></span>|  
|<span data-ttu-id="43ec6-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="43ec6-106">**Issue**</span></span>|<span data-ttu-id="43ec6-107">Algunas réplicas de disponibilidad no tienen un rol en buen estado.</span><span class="sxs-lookup"><span data-stu-id="43ec6-107">Some availability replicas do not have a healthy role.</span></span>|  
|<span data-ttu-id="43ec6-108">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="43ec6-108">**Category**</span></span>|<span data-ttu-id="43ec6-109">**Warning (ADVERTENCIA)**</span><span class="sxs-lookup"><span data-stu-id="43ec6-109">**Warning**</span></span>|  
|<span data-ttu-id="43ec6-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="43ec6-110">**Facet**</span></span>|<span data-ttu-id="43ec6-111">grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="43ec6-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="43ec6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="43ec6-112">Description</span></span>  
 <span data-ttu-id="43ec6-113">Esta directiva acumula el estado de conexión de todas las réplicas de disponibilidad y comprueba si hay alguna réplica de disponibilidad que no está en un rol correcto.</span><span class="sxs-lookup"><span data-stu-id="43ec6-113">This policy rolls up the connection state of all availability replicas and checks if there are any availability replicas that are not in a healthy role.</span></span> <span data-ttu-id="43ec6-114">La directiva está en mal estado cuando una réplica de disponibilidad no es principal ni secundaria.</span><span class="sxs-lookup"><span data-stu-id="43ec6-114">The policy is in an unhealthy state when any availability replica is neither primary nor secondary.</span></span> <span data-ttu-id="43ec6-115">De lo contrario, la directiva está en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="43ec6-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43ec6-116">En esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [Algunas réplicas de disponibilidad no tienen un rol correcto](https://go.microsoft.com/fwlink/p/?LinkId=220854) en la wiki de TechNet.</span><span class="sxs-lookup"><span data-stu-id="43ec6-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas do not have a healthy role](https://go.microsoft.com/fwlink/p/?LinkId=220854) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="43ec6-117">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="43ec6-117">Possible Causes</span></span>  
 <span data-ttu-id="43ec6-118">En este grupo de disponibilidad, al menos una réplica de disponibilidad no tiene actualmente el rol principal o secundario.</span><span class="sxs-lookup"><span data-stu-id="43ec6-118">In this availability group, at least one availability replica does not currently have the primary or secondary role.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="43ec6-119">Solución posible</span><span class="sxs-lookup"><span data-stu-id="43ec6-119">Possible Solution</span></span>  
 <span data-ttu-id="43ec6-120">Use el estado de la directiva de réplica de disponibilidad para buscar la réplica de disponibilidad cuyo rol no es principal ni secundario, y después resuelva el problema en la réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="43ec6-120">Use the availability replica policy state to find the availability replica whose role is not primary or secondary, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43ec6-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43ec6-121">See Also</span></span>  
 <span data-ttu-id="43ec6-122">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="43ec6-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="43ec6-123">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="43ec6-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
