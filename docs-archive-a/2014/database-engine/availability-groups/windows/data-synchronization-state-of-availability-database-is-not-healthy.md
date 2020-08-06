---
title: El estado de sincronización de datos de bases de datos de disponibilidad no es correcto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp3datasynchealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 4fd003e7-808e-4b0e-b28a-47d9f2616f06
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a179008c20b108a2f6aaefd5dd80b22708e94a8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752345"
---
# <a name="data-synchronization-state-of-availability-database-is-not-healthy"></a><span data-ttu-id="6780a-102">El estado de sincronización de datos de bases de datos de disponibilidad no está en buen estado</span><span class="sxs-lookup"><span data-stu-id="6780a-102">Data synchronization state of availability database is not healthy</span></span>
    
## <a name="introduction"></a><span data-ttu-id="6780a-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="6780a-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6780a-104">**Nombre de directiva**</span><span class="sxs-lookup"><span data-stu-id="6780a-104">**Policy Name**</span></span>|<span data-ttu-id="6780a-105">Estado de sincronización de datos de la base de datos de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="6780a-105">Availability Database Data Synchronization State</span></span>|  
|<span data-ttu-id="6780a-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="6780a-106">**Issue**</span></span>|<span data-ttu-id="6780a-107">El estado de sincronización de datos de las bases de datos de disponibilidad no es correcto</span><span class="sxs-lookup"><span data-stu-id="6780a-107">Data synchronization state of availability database is not healthy.</span></span>|  
|<span data-ttu-id="6780a-108">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="6780a-108">**Category**</span></span>|<span data-ttu-id="6780a-109">**Warning (ADVERTENCIA)**</span><span class="sxs-lookup"><span data-stu-id="6780a-109">**Warning**</span></span>|  
|<span data-ttu-id="6780a-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="6780a-110">**Facet**</span></span>|<span data-ttu-id="6780a-111">Base de datos de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="6780a-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6780a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6780a-112">Description</span></span>  
 <span data-ttu-id="6780a-113">Esta directiva acumula el estado de sincronización de datos de todas las bases de datos de disponibilidad (también conocidas como "réplicas de base de datos") en la réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="6780a-113">This policy rolls up the data synchronization state of all availability databases (also known as "database replicas") in the availability replica.</span></span> <span data-ttu-id="6780a-114">La directiva está en mal estado cuando alguna réplica de la base de datos no está en el estado esperado de sincronización de datos.</span><span class="sxs-lookup"><span data-stu-id="6780a-114">The policy is in an unhealthy sate when any database replica is not in the expected data synchronization state.</span></span> <span data-ttu-id="6780a-115">De lo contrario, la directiva está en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="6780a-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6780a-116">Para esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [El estado de sincronización de datos de alguna base de datos de disponibilidad no está en buen estado](https://go.microsoft.com/fwlink/p/?LinkId=220858) en TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="6780a-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Data synchronization state of some availability database is not healthy](https://go.microsoft.com/fwlink/p/?LinkId=220858) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="6780a-117">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="6780a-117">Possible Causes</span></span>  
 <span data-ttu-id="6780a-118">El estado de sincronización de datos de esta base de datos de disponibilidad no es correcto.</span><span class="sxs-lookup"><span data-stu-id="6780a-118">The data synchronization state of this availability database is unhealthy.</span></span> <span data-ttu-id="6780a-119">En una réplica de disponibilidad de confirmación asincrónica, cada base de datos de disponibilidad debe estar en el estado SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="6780a-119">On an asynchronous-commit availability replica, every availability database should be in the SYNCHRONIZING state.</span></span> <span data-ttu-id="6780a-120">En una réplica de confirmación sincrónica, cada base de datos de disponibilidad debe estar en el estado SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="6780a-120">On a synchronous-commit replica, every availability database must be in the SYNCHRONIZED state.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="6780a-121">Solución posible</span><span class="sxs-lookup"><span data-stu-id="6780a-121">Possible Solution</span></span>  
 <span data-ttu-id="6780a-122">Use la directiva de réplica de base de datos para buscar la réplica de base de datos que está en un estado incorrecto de sincronización de datos y, a continuación, resuelva el problema en la réplica de base de datos.</span><span class="sxs-lookup"><span data-stu-id="6780a-122">Use the database replica policy to find the database replica with an unhealthy data synchronization state, and then resolve the issue at the database replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6780a-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6780a-123">See Also</span></span>  
 <span data-ttu-id="6780a-124">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6780a-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="6780a-125">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6780a-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
