---
title: Réplica de disponibilidad desconectada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp2connected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 1a2162d3-54fb-4356-b349-effbdc15a5a4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1db92b8e73b6daaee7edf5042b1d73cfeb471d1d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746535"
---
# <a name="availability-replica-is-disconnected"></a><span data-ttu-id="28a60-102">Réplica de disponibilidad desconectada</span><span class="sxs-lookup"><span data-stu-id="28a60-102">Availability replica is disconnected</span></span>
    
## <a name="introduction"></a><span data-ttu-id="28a60-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="28a60-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28a60-104">**Nombre de directiva**</span><span class="sxs-lookup"><span data-stu-id="28a60-104">**Policy Name**</span></span>|<span data-ttu-id="28a60-105">Estado de conexión de la réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="28a60-105">Availability Replica Connection State</span></span>|  
|<span data-ttu-id="28a60-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="28a60-106">**Issue**</span></span>|<span data-ttu-id="28a60-107">La réplica de disponibilidad está desconectada.</span><span class="sxs-lookup"><span data-stu-id="28a60-107">Availability replica is disconnected.</span></span>|  
|<span data-ttu-id="28a60-108">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="28a60-108">**Category**</span></span>|<span data-ttu-id="28a60-109">**Critical)** (Crítico)</span><span class="sxs-lookup"><span data-stu-id="28a60-109">**Critical**</span></span>|  
|<span data-ttu-id="28a60-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="28a60-110">**Facet**</span></span>|<span data-ttu-id="28a60-111">réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="28a60-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="28a60-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="28a60-112">Description</span></span>  
 <span data-ttu-id="28a60-113">Esta directiva comprueba el estado de conexión entre las réplicas de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="28a60-113">This policy checks the connection state between availability replicas.</span></span> <span data-ttu-id="28a60-114">La directiva está en mal estado cuando el estado de conexión de la réplica de disponibilidad es DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="28a60-114">The policy is in an unhealthy state when the connection state of the availability replica is DISCONNECTED.</span></span> <span data-ttu-id="28a60-115">De lo contrario, la directiva está en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="28a60-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28a60-116"> Para esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [La réplica de disponibilidad está desconectada](https://go.microsoft.com/fwlink/p/?LinkId=220857) en TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="28a60-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica is disconnected](https://go.microsoft.com/fwlink/p/?LinkId=220857) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="28a60-117">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="28a60-117">Possible Causes</span></span>  
 <span data-ttu-id="28a60-118">La réplica secundaria no está conectada a la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="28a60-118">The secondary replica is not connected to the primary replica.</span></span> <span data-ttu-id="28a60-119">El estado de conexión es DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="28a60-119">The connected state is DISCONNECTED.</span></span> <span data-ttu-id="28a60-120">Este problema puede deberse a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="28a60-120">This issue can be caused by the following:</span></span>  
  
-   <span data-ttu-id="28a60-121">El puerto de conexión puede estar en conflicto con otra aplicación.</span><span class="sxs-lookup"><span data-stu-id="28a60-121">The connection port might be in conflict with another application.</span></span>  
  
-   <span data-ttu-id="28a60-122">El tipo de cifrado o el algoritmo no coinciden.</span><span class="sxs-lookup"><span data-stu-id="28a60-122">The encryption type or algorithm is mismatched.</span></span>  
  
-   <span data-ttu-id="28a60-123">Se ha eliminado o no se ha iniciado el extremo de la conexión.</span><span class="sxs-lookup"><span data-stu-id="28a60-123">The connection endpoint has been deleted or has not been started.</span></span>  
  
-   <span data-ttu-id="28a60-124">El transporte está desconectado.</span><span class="sxs-lookup"><span data-stu-id="28a60-124">The transport is disconnected.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="28a60-125">Soluciones posibles</span><span class="sxs-lookup"><span data-stu-id="28a60-125">Possible Solutions</span></span>  
 <span data-ttu-id="28a60-126">Las siguientes son posibles soluciones para este problema:</span><span class="sxs-lookup"><span data-stu-id="28a60-126">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="28a60-127">Compruebe la configuración del extremo de creación de reflejo de la base de datos para las instancias de la réplica principal y secundaria, y actualice la configuración que no coincide.</span><span class="sxs-lookup"><span data-stu-id="28a60-127">Check the database mirroring endpoint configuration for the instances of the primary and secondary replica and update the mismatched configuration.</span></span>  
  
-   <span data-ttu-id="28a60-128">Compruebe si el puerto está en conflicto y, si en ese caso, cambie el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="28a60-128">Check if the port is conflicting, and if so, change the port number.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a60-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="28a60-129">See Also</span></span>  
 <span data-ttu-id="28a60-130">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="28a60-130">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="28a60-131">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="28a60-131">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
