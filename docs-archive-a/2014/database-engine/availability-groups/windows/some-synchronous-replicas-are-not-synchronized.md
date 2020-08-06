---
title: Algunas réplicas sincrónicas no están sincronizadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp5synchronized.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: e58ed56e-4c30-42e6-a9fc-a8c401620e02
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ecef2d16e80e128834a71e1f1f112096f8ccc9cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673272"
---
# <a name="some-synchronous-replicas-are-not-synchronized"></a><span data-ttu-id="c9423-102">Algunas réplicas sincrónicas no están sincronizadas</span><span class="sxs-lookup"><span data-stu-id="c9423-102">Some synchronous replicas are not synchronized</span></span>
    
## <a name="introduction"></a><span data-ttu-id="c9423-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="c9423-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9423-104">**Nombre de directiva**</span><span class="sxs-lookup"><span data-stu-id="c9423-104">**Policy Name**</span></span>|<span data-ttu-id="c9423-105">Estado de sincronización de los datos de réplicas sincrónicas</span><span class="sxs-lookup"><span data-stu-id="c9423-105">Synchronous Replicas Data Synchronization State</span></span>|  
|<span data-ttu-id="c9423-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c9423-106">**Issue**</span></span>|<span data-ttu-id="c9423-107">Algunas réplicas sincrónicas no están sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="c9423-107">Some synchronous replicas are not synchronized.</span></span>|  
|<span data-ttu-id="c9423-108">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="c9423-108">**Category**</span></span>|<span data-ttu-id="c9423-109">**Warning (ADVERTENCIA)**</span><span class="sxs-lookup"><span data-stu-id="c9423-109">**Warning**</span></span>|  
|<span data-ttu-id="c9423-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="c9423-110">**Facet**</span></span>|<span data-ttu-id="c9423-111">grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="c9423-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c9423-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9423-112">Description</span></span>  
 <span data-ttu-id="c9423-113">Esta directiva acumula el estado de sincronización de datos de todas las réplicas de disponibilidad y comprueba que no están en el estado de sincronización esperado.</span><span class="sxs-lookup"><span data-stu-id="c9423-113">This policy rolls up the data synchronization state of all availability replicas and checks for any availability replicas that are not in the expected synchronization state.</span></span> <span data-ttu-id="c9423-114">La directiva está en mal estado cuando alguna réplica asincrónica no está en un estado SYNCHRONIZING y alguna réplica sincrónica no tiene un estado SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="c9423-114">The policy is in an unhealthy state when any asynchronous replica is not in a SYNCHRONIZING state and any synchronous replica is not in a SYNCHRONIZED state.</span></span> <span data-ttu-id="c9423-115">De lo contrario, el estado de la directiva es correcto.</span><span class="sxs-lookup"><span data-stu-id="c9423-115">The policy state is otherwise healthy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9423-116">En esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [Algunas réplicas sincrónicas no están sincronizadas](https://go.microsoft.com/fwlink/p/?LinkId=220853) en TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="c9423-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some synchronous replicas are not synchronized](https://go.microsoft.com/fwlink/p/?LinkId=220853) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="c9423-117">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="c9423-117">Possible Causes</span></span>  
 <span data-ttu-id="c9423-118">En este grupo de disponibilidad, al menos una réplica sincrónica no está sincronizada actualmente.</span><span class="sxs-lookup"><span data-stu-id="c9423-118">In this availability group, at least one synchronous replica is not currently synchronized.</span></span> <span data-ttu-id="c9423-119">El estado de sincronización de la réplica puede ser SYNCHRONIZING o NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="c9423-119">The replica synchronization state could be either SYNCHONIZING or NOT SYNCHRONIZING.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="c9423-120">Solución posible</span><span class="sxs-lookup"><span data-stu-id="c9423-120">Possible Solution</span></span>  
 <span data-ttu-id="c9423-121">Use el estado de la directiva de réplica de disponibilidad para buscar la réplica de disponibilidad cuyo estado de sincronización es incorrecto, y después resuelva el problema en la réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="c9423-121">Use the availability replica policy state to find the availability replica with the incorrect synchronization state, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9423-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c9423-122">See Also</span></span>  
 <span data-ttu-id="c9423-123">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c9423-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="c9423-124">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="c9423-124">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
