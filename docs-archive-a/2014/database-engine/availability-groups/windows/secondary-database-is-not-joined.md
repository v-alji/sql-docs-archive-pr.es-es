---
title: Base de datos secundaria sin combinar | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp2joined.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 10817e5e-75fa-42dd-baa2-359bea3ad051
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 81275e85fd865924778f6d6f985e170a5bda9f9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749487"
---
# <a name="secondary-database-is-not-joined"></a><span data-ttu-id="04a66-102">Base de datos secundaria sin combinar</span><span class="sxs-lookup"><span data-stu-id="04a66-102">Secondary database is not joined</span></span>
    
## <a name="introduction"></a><span data-ttu-id="04a66-103">Introducción</span><span class="sxs-lookup"><span data-stu-id="04a66-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04a66-104">**Nombre de directiva**</span><span class="sxs-lookup"><span data-stu-id="04a66-104">**Policy Name**</span></span>|<span data-ttu-id="04a66-105">Estado de combinación de la base de datos de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="04a66-105">Availability Database Join State</span></span>|  
|<span data-ttu-id="04a66-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="04a66-106">**Issue**</span></span>|<span data-ttu-id="04a66-107">Base de datos secundaria sin combinar.</span><span class="sxs-lookup"><span data-stu-id="04a66-107">Secondary database is not joined.</span></span>|  
|<span data-ttu-id="04a66-108">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="04a66-108">**Category**</span></span>|<span data-ttu-id="04a66-109">**Warning (ADVERTENCIA)**</span><span class="sxs-lookup"><span data-stu-id="04a66-109">**Warning**</span></span>|  
|<span data-ttu-id="04a66-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="04a66-110">**Facet**</span></span>|<span data-ttu-id="04a66-111">Base de datos de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="04a66-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="04a66-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="04a66-112">Description</span></span>  
 <span data-ttu-id="04a66-113">Esta directiva comprueba el estado de la unión de la base de datos secundaria (también denominada “réplica de base de datos secundaria”).</span><span class="sxs-lookup"><span data-stu-id="04a66-113">This policy checks the join state of the secondary database (also known as a "secondary database replica").</span></span> <span data-ttu-id="04a66-114">La directiva está en mal estado cuando la réplica de conjunto de datos no está combinada.</span><span class="sxs-lookup"><span data-stu-id="04a66-114">The policy is in an unhealthy state when the dataset replica is not joined.</span></span> <span data-ttu-id="04a66-115">De lo contrario, la directiva está en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="04a66-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04a66-116">Para esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [La base de datos secundaria no se ha combinado](https://go.microsoft.com/fwlink/p/?LinkId=220862) en TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="04a66-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Secondary database is not joined](https://go.microsoft.com/fwlink/p/?LinkId=220862) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="04a66-117">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="04a66-117">Possible Causes</span></span>  
 <span data-ttu-id="04a66-118">Esta base de datos secundaria no está combinada con el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="04a66-118">This secondary database is not joined to the availability group.</span></span> <span data-ttu-id="04a66-119">La configuración de esta base de datos secundaria está incompleta.</span><span class="sxs-lookup"><span data-stu-id="04a66-119">The configuration of this secondary database is incomplete.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="04a66-120">Solución posible</span><span class="sxs-lookup"><span data-stu-id="04a66-120">Possible Solution</span></span>  
 <span data-ttu-id="04a66-121">Use Transact-SQL, PowerShell o SQL Server Management Studio para combinar la réplica secundaria con el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="04a66-121">Use Transact-SQL, PowerShell, or SQL Server Management Studio to join the secondary replica to the availability group.</span></span> <span data-ttu-id="04a66-122">Para obtener más información sobre cómo combinar las réplicas secundarias con los grupos de disponibilidad, vea [Combinar una réplica secundaria con un grupo de disponibilidad (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="04a66-122">For more information about joining secondary replicas to availability groups, see [Joining a Secondary Replica to an Availability Group (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a66-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04a66-123">See Also</span></span>  
 <span data-ttu-id="04a66-124">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="04a66-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="04a66-125">Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="04a66-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
