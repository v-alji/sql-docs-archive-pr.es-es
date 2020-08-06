---
title: El estado de sincronización de datos de alguna base de datos de disponibilidad no es correcto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp3datasynchealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 89f95d15-33c6-4768-bccd-9dbf8c4f49a9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 221f25a1ee7e4a8719acc133372c742ca4a79303
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752334"
---
# <a name="data-synchronization-state-of-some-availability-database-is-not-healthy"></a><span data-ttu-id="93ca5-102">El estado de sincronización de datos de alguna base de datos de disponibilidad no está en buen estado</span><span class="sxs-lookup"><span data-stu-id="93ca5-102">Data synchronization state of some availability database is not healthy</span></span>
    
## <a name="introduction"></a><span data-ttu-id="93ca5-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="93ca5-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="93ca5-104">**Nombre de directiva**</span><span class="sxs-lookup"><span data-stu-id="93ca5-104">**Policy Name**</span></span>|<span data-ttu-id="93ca5-105">Estado de sincronización de datos de las réplicas de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="93ca5-105">Availability Replica Data Synchronization State</span></span>|  
|<span data-ttu-id="93ca5-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="93ca5-106">**Issue**</span></span>|<span data-ttu-id="93ca5-107">El estado de sincronización de datos de alguna base de datos de disponibilidad no es correcto.</span><span class="sxs-lookup"><span data-stu-id="93ca5-107">Data synchronization state of some availability database is not healthy.</span></span>|  
|<span data-ttu-id="93ca5-108">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="93ca5-108">**Category**</span></span>|<span data-ttu-id="93ca5-109">**Warning (ADVERTENCIA)**</span><span class="sxs-lookup"><span data-stu-id="93ca5-109">**Warning**</span></span>|  
|<span data-ttu-id="93ca5-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="93ca5-110">**Facet**</span></span>|<span data-ttu-id="93ca5-111">réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="93ca5-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="93ca5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="93ca5-112">Description</span></span>  
 <span data-ttu-id="93ca5-113">Esta directiva comprueba el estado de sincronización de datos de la base de datos de disponibilidad (también denominada “réplica de base de datos”).</span><span class="sxs-lookup"><span data-stu-id="93ca5-113">This policy checks the data synchronization state of the availability database (also known as a "database replica").</span></span> <span data-ttu-id="93ca5-114">La directiva está en mal estado cuando el estado de sincronización de datos es NOT SYNCHRONIZING o cuando no es SYNCHRONIZED para la réplica de base de datos de confirmación sincrónica.</span><span class="sxs-lookup"><span data-stu-id="93ca5-114">The policy is in an unhealthy state when the data synchronization state is NOT SYNCHRONIZING or the state is not SYNCHRONIZED for the synchronous-commit database replica.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93ca5-115">Para esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en [El estado de sincronización de datos de la base de datos de disponibilidad no es correcto](https://go.microsoft.com/fwlink/p/?LinkId=220863) en la wiki de TechNet.</span><span class="sxs-lookup"><span data-stu-id="93ca5-115">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Data synchronization state of availability database is not healthy](https://go.microsoft.com/fwlink/p/?LinkId=220863) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="93ca5-116">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="93ca5-116">Possible Causes</span></span>  
 <span data-ttu-id="93ca5-117">Al menos una base de datos de disponibilidad en la réplica tiene un estado incorrecto de sincronización de datos.</span><span class="sxs-lookup"><span data-stu-id="93ca5-117">At least one availability database on the replica has an unhealthy data synchronization state.</span></span> <span data-ttu-id="93ca5-118">Si se trata de una réplica de disponibilidad de confirmación asincrónica, todas las bases de datos de disponibilidad deben estar en el estado SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="93ca5-118">If this is an asynchronous-commit availability replica, all availability databases should be in the SYNCHRONIZING state.</span></span> <span data-ttu-id="93ca5-119">Si se trata de una réplica de disponibilidad de confirmación sincrónica, todas las bases de datos de disponibilidad deben estar en el estado SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="93ca5-119">If this is a synchronous-commit availability replica, all availability databases should be in the SYNCHRONIZED state.</span></span> <span data-ttu-id="93ca5-120">Este problema puede deberse a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="93ca5-120">This issue can be caused by the following:</span></span>  
  
-   <span data-ttu-id="93ca5-121">La réplica de disponibilidad puede estar desconectada.</span><span class="sxs-lookup"><span data-stu-id="93ca5-121">The availability replica might be disconnected.</span></span>  
  
-   <span data-ttu-id="93ca5-122">El movimiento de datos puede haberse suspendido.</span><span class="sxs-lookup"><span data-stu-id="93ca5-122">The data movement might be suspended.</span></span>  
  
-   <span data-ttu-id="93ca5-123">La base de datos no está accesible.</span><span class="sxs-lookup"><span data-stu-id="93ca5-123">The database might not be accessible.</span></span>  
  
-   <span data-ttu-id="93ca5-124">Puede haber un problema de retraso temporal debido a la latencia de red o a la carga en la réplica principal o secundaria.</span><span class="sxs-lookup"><span data-stu-id="93ca5-124">There might be a temporary delay issue due to network latency or the load on the primary or secondary replica.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="93ca5-125">Solución posible</span><span class="sxs-lookup"><span data-stu-id="93ca5-125">Possible Solution</span></span>  
 <span data-ttu-id="93ca5-126">Resuelva cualquier problema de suspensión de conexión o de movimiento de datos.</span><span class="sxs-lookup"><span data-stu-id="93ca5-126">Resolve any connection or data movement suspend issues.</span></span> <span data-ttu-id="93ca5-127">Compruebe los eventos correspondientes a este problema mediante SQL Server Management Studio y busque el error de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="93ca5-127">Check the events for this issue using SQL Server Management Studio, and find the database error.</span></span> <span data-ttu-id="93ca5-128">Realice los siguientes pasos para solucionar problemas del error concreto.</span><span class="sxs-lookup"><span data-stu-id="93ca5-128">Follow the troubleshooting steps for the specific error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93ca5-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93ca5-129">See Also</span></span>  
 <span data-ttu-id="93ca5-130">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="93ca5-130">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="93ca5-131">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="93ca5-131">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
