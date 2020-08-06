---
title: La réplica de disponibilidad no tiene un rol en buen estado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp1rolehealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: ebb2c9f4-2097-4688-b4fb-8f0571047317
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7be26945903a5e3b602ef4a99c269de6a58b04a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746538"
---
# <a name="availability-replica-does-not-have-a-healthy-role"></a><span data-ttu-id="c4e00-102">La réplica de disponibilidad no tiene un rol en buen estado</span><span class="sxs-lookup"><span data-stu-id="c4e00-102">Availability replica does not have a healthy role</span></span>
    
## <a name="introduction"></a><span data-ttu-id="c4e00-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="c4e00-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c4e00-104">**Nombre de directiva**</span><span class="sxs-lookup"><span data-stu-id="c4e00-104">**Policy Name**</span></span>|<span data-ttu-id="c4e00-105">Estado del rol de réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="c4e00-105">Availability Replica Role State</span></span>|  
|<span data-ttu-id="c4e00-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c4e00-106">**Issue**</span></span>|<span data-ttu-id="c4e00-107">La réplica de disponibilidad no tiene un rol en buen estado.</span><span class="sxs-lookup"><span data-stu-id="c4e00-107">Availability replica does not have a healthy role.</span></span>|  
|<span data-ttu-id="c4e00-108">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="c4e00-108">**Category**</span></span>|<span data-ttu-id="c4e00-109">**Critical)** (Crítico)</span><span class="sxs-lookup"><span data-stu-id="c4e00-109">**Critical**</span></span>|  
|<span data-ttu-id="c4e00-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="c4e00-110">**Facet**</span></span>|<span data-ttu-id="c4e00-111">réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="c4e00-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c4e00-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4e00-112">Description</span></span>  
 <span data-ttu-id="c4e00-113">Esta directiva comprueba el estado del rol de la réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="c4e00-113">This policy checks the state of the role of the availability replica.</span></span> <span data-ttu-id="c4e00-114">La directiva está en mal estado cuando el rol de la réplica de disponibilidad no es principal ni secundario.</span><span class="sxs-lookup"><span data-stu-id="c4e00-114">The policy is in an unhealthy state when the role of the availability replica is neither primary nor secondary.</span></span> <span data-ttu-id="c4e00-115">De lo contrario, la directiva está en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="c4e00-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4e00-116">En esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [La réplica de disponibilidad no tiene un rol en buen estado](https://go.microsoft.com/fwlink/p/?LinkId=220856) en TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="c4e00-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica does not have a healthy role](https://go.microsoft.com/fwlink/p/?LinkId=220856) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="c4e00-117">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="c4e00-117">Possible Causes</span></span>  
 <span data-ttu-id="c4e00-118">El rol de esta réplica de disponibilidad está en mal estado.</span><span class="sxs-lookup"><span data-stu-id="c4e00-118">The role of this availability replica is unhealthy.</span></span> <span data-ttu-id="c4e00-119">La réplica no tiene el rol principal o secundario.</span><span class="sxs-lookup"><span data-stu-id="c4e00-119">The replica does not have either the primary or secondary role.</span></span>  
  
## <a name="possible-solution-information_still_to_come"></a><span data-ttu-id="c4e00-120">Solución posible: Information_still_to_come</span><span class="sxs-lookup"><span data-stu-id="c4e00-120">Possible Solution: Information_still_to_come</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e00-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4e00-121">See Also</span></span>  
 <span data-ttu-id="c4e00-122">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c4e00-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="c4e00-123">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="c4e00-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
