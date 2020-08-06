---
title: Algunas réplicas de disponibilidad no sincronizan datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp4synchronizing.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 3db6a569-e942-4321-a0dd-c4ab002087c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 762b7da1f7b8a07257c2a900307eb1bb10408653
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673278"
---
# <a name="some-availability-replicas-are-not-synchronizing-data"></a><span data-ttu-id="5e72b-102">Algunas réplicas de disponibilidad no sincronizan datos</span><span class="sxs-lookup"><span data-stu-id="5e72b-102">Some availability replicas are not synchronizing data</span></span>
    
## <a name="introduction"></a><span data-ttu-id="5e72b-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="5e72b-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5e72b-104">**Nombre de directiva**</span><span class="sxs-lookup"><span data-stu-id="5e72b-104">**Policy Name**</span></span>|<span data-ttu-id="5e72b-105">Estado de sincronización de datos de las réplicas de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="5e72b-105">Availability Replicas Data Synchronization State</span></span>|  
|<span data-ttu-id="5e72b-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e72b-106">**Issue**</span></span>|<span data-ttu-id="5e72b-107">Algunas réplicas de disponibilidad no sincronizan datos.</span><span class="sxs-lookup"><span data-stu-id="5e72b-107">Some availability replicas are not synchronizing data.</span></span>|  
|<span data-ttu-id="5e72b-108">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="5e72b-108">**Category**</span></span>|<span data-ttu-id="5e72b-109">**Warning (ADVERTENCIA)**</span><span class="sxs-lookup"><span data-stu-id="5e72b-109">**Warning**</span></span>|  
|<span data-ttu-id="5e72b-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="5e72b-110">**Facet**</span></span>|<span data-ttu-id="5e72b-111">grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="5e72b-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5e72b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e72b-112">Description</span></span>  
 <span data-ttu-id="5e72b-113">Esta directiva acumula el estado de sincronización de datos de todas las réplicas de disponibilidad en el grupo de disponibilidad y comprueba si la sincronización de alguna réplica de disponibilidad no está operativa.</span><span class="sxs-lookup"><span data-stu-id="5e72b-113">This policy rolls up the data synchronization state of all availability replicas in the availability group and checks if the synchronization of any availability replica is not operational.</span></span> <span data-ttu-id="5e72b-114">La directiva está en mal estado si alguno de los estados de sincronización de datos de la réplica de disponibilidad es NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="5e72b-114">The policy is in an unhealthy state if any of the data synchronization states of the availability replica is NOT SYNCRONIZING.</span></span>  
  
 <span data-ttu-id="5e72b-115">Esta directiva está en un estado correcto si ninguno de los estados de sincronización de datos de la réplica de disponibilidad es NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="5e72b-115">This policy is in a healthy state if none of the data synchronization states of the availability replica is NOT SYNCHRONIZING.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e72b-116">Para esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [Algunas réplicas de disponibilidad no sincronizan datos](https://go.microsoft.com/fwlink/p/?LinkId=220852) de la wiki de TechNet.</span><span class="sxs-lookup"><span data-stu-id="5e72b-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas are not synchronizing data](https://go.microsoft.com/fwlink/p/?LinkId=220852) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="5e72b-117">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="5e72b-117">Possible Causes</span></span>  
 <span data-ttu-id="5e72b-118">En este grupo de disponibilidad, al menos una réplica secundaria tiene un estado de sincronización NOT SYNCHRONIZING y no recibe datos de la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="5e72b-118">In this availability group, at least one secondary replica has a NOT SYNCHRONIZING synchronization state and is not receiving data from the primary replica.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="5e72b-119">Solución posible</span><span class="sxs-lookup"><span data-stu-id="5e72b-119">Possible Solution</span></span>  
 <span data-ttu-id="5e72b-120">Use el estado de directiva de la réplica de disponibilidad para buscar la réplica de disponibilidad con un estado NOT SYNCHRONIZING y, a continuación, resuelva el problema en la réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="5e72b-120">Use the availability replica policy state to find the availability replica with a NOT SYNCHROINIZING state, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e72b-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e72b-121">See Also</span></span>  
 <span data-ttu-id="5e72b-122">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5e72b-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="5e72b-123">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5e72b-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
