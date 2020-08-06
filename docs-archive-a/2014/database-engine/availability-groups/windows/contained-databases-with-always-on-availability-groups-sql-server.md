---
title: Bases de datos independientes con grupos de disponibilidad AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- contained database [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: cacce3ae-e940-4566-8298-6607c4268e74
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 74c8a0b41ee7224dad83fb41691a4898c15b7b38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663126"
---
# <a name="contained-databases-with-always-on-availability-groups-sql-server"></a><span data-ttu-id="13b39-102">Bases de datos independientes con grupos de disponibilidad AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="13b39-102">Contained Databases with Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="13b39-103">Este tema contiene información sobre cómo utilizar una base de datos independiente con [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13b39-103">This topic contains information about the using a contained database with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="13b39-104">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="13b39-104">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="13b39-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="13b39-105">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="13b39-106">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="13b39-106">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="13b39-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="13b39-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="13b39-108">Antes de agregar una base de datos independiente a un grupo de disponibilidad, asegúrese de que la opción de servidor `contained database authentication` está establecida en `1` en cada instancia de servidor que hospeda una réplica de disponibilidad para el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="13b39-108">Before adding a contained database to an availability group, ensure that the `contained database authentication` server option is set to `1` on every server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="13b39-109">Para obtener más información, vea [contained database authentication (opción de configuración del servidor)](../../configure-windows/contained-database-authentication-server-configuration-option.md) y [Opciones de configuración de servidor &#40;SQL Server&#41;](../../configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="13b39-109">For more information, see [contained database authentication Server Configuration Option](../../configure-windows/contained-database-authentication-server-configuration-option.md) and [Server Configuration Options &#40;SQL Server&#41;](../../configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="13b39-110">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="13b39-110">Related Tasks</span></span>  
  
-   [<span data-ttu-id="13b39-111">Opciones de configuración de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="13b39-111">Server Configuration Options &#40;SQL Server&#41;</span></span>](../../configure-windows/server-configuration-options-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="13b39-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13b39-112">See Also</span></span>  
 <span data-ttu-id="13b39-113">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="13b39-113">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="13b39-114">Bases de datos independientes</span><span class="sxs-lookup"><span data-stu-id="13b39-114">Contained Databases</span></span>](../../../relational-databases/databases/contained-databases.md)  
  
  
