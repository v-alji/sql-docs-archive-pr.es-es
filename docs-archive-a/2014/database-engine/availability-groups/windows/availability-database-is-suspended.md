---
title: Base de datos de disponibilidad suspendida | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp1notsuspended.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 6baee70f-848c-4e86-b20d-78875c0f82cb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07a547f217367f13df739348325461c862d831f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663143"
---
# <a name="availability-database-is-suspended"></a><span data-ttu-id="9cbdf-102">Base de datos de disponibilidad suspendida</span><span class="sxs-lookup"><span data-stu-id="9cbdf-102">Availability database is suspended</span></span>
    
## <a name="introduction"></a><span data-ttu-id="9cbdf-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="9cbdf-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9cbdf-104">**Nombre de directiva**</span><span class="sxs-lookup"><span data-stu-id="9cbdf-104">**Policy Name**</span></span>|<span data-ttu-id="9cbdf-105">Estado de suspensión de la base de datos de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="9cbdf-105">Availability Database Suspension State</span></span>|  
|<span data-ttu-id="9cbdf-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="9cbdf-106">**Issue**</span></span>|<span data-ttu-id="9cbdf-107">Base de datos de disponibilidad suspendida.</span><span class="sxs-lookup"><span data-stu-id="9cbdf-107">Availability database is suspended.</span></span>|  
|<span data-ttu-id="9cbdf-108">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="9cbdf-108">**Category**</span></span>|<span data-ttu-id="9cbdf-109">**Warning (ADVERTENCIA)**</span><span class="sxs-lookup"><span data-stu-id="9cbdf-109">**Warning**</span></span>|  
|<span data-ttu-id="9cbdf-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="9cbdf-110">**Facet**</span></span>|<span data-ttu-id="9cbdf-111">Base de datos de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="9cbdf-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9cbdf-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9cbdf-112">Description</span></span>  
 <span data-ttu-id="9cbdf-113">Esta directiva comprueba el estado del movimiento de datos de la base de datos secundaria (también denominada “réplica de base de datos secundaria”).</span><span class="sxs-lookup"><span data-stu-id="9cbdf-113">This policy checks the state of data movement of the secondary database (also known as a "secondary database replica").</span></span> <span data-ttu-id="9cbdf-114">La directiva está en mal estado cuando se suspende el movimiento de datos.</span><span class="sxs-lookup"><span data-stu-id="9cbdf-114">The policy is in an unhealthy state when the data movement is suspended.</span></span> <span data-ttu-id="9cbdf-115">De lo contrario, la directiva está en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="9cbdf-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9cbdf-116"> Para esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [La base de datos de disponibilidad se ha suspendido](https://go.microsoft.com/fwlink/p/?LinkId=220860) en TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="9cbdf-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability database is suspended](https://go.microsoft.com/fwlink/p/?LinkId=220860) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="9cbdf-117">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="9cbdf-117">Possible Causes</span></span>  
 <span data-ttu-id="9cbdf-118">La sincronización de datos de esta base de datos de disponibilidad podría haberse suspendido debido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="9cbdf-118">Data synchronization on this availability database might have been suspended because of the following:</span></span>  
  
-   <span data-ttu-id="9cbdf-119">Debido a un error, el sistema puede haber suspendido la sincronización de datos.</span><span class="sxs-lookup"><span data-stu-id="9cbdf-119">Due to an error, the system might have suspended data synchronization.</span></span>  
  
-   <span data-ttu-id="9cbdf-120">El administrador de la base de datos puede haber suspendido la sincronización de datos con fines de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="9cbdf-120">The database administrator might have suspended data synchronization for maintenance purposes.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="9cbdf-121">Solución posible</span><span class="sxs-lookup"><span data-stu-id="9cbdf-121">Possible Solution</span></span>  
 <span data-ttu-id="9cbdf-122">Reanude la sincronización de datos.</span><span class="sxs-lookup"><span data-stu-id="9cbdf-122">Resume data synchronization.</span></span> <span data-ttu-id="9cbdf-123">Si el problema persiste, compruebe el grupo de disponibilidad en el registro de eventos y, a continuación, diagnostique por qué el sistema suspendió el movimiento de datos.</span><span class="sxs-lookup"><span data-stu-id="9cbdf-123">If the issue persists, check the availability group in the Event log, and then diagnose why the system suspended data movement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cbdf-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9cbdf-124">See Also</span></span>  
 <span data-ttu-id="9cbdf-125">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9cbdf-125">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="9cbdf-126">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9cbdf-126">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
