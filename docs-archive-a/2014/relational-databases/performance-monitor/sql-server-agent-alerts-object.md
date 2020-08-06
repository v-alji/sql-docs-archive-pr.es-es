---
title: Alerts (objeto del Agente SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Alerts object
- SQLAgent:Alerts
ms.assetid: e5e37f74-ee88-46d0-ad8f-71fd1b1fa64a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9aa6fa871730af8cf129b3ea6b0aa4f1853d7e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670345"
---
# <a name="sql-server-agent-alerts-object"></a><span data-ttu-id="bb7ef-102">Alerts (objeto del Agente SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bb7ef-102">SQL Server Agent, Alerts Object</span></span>
  <span data-ttu-id="bb7ef-103">El objeto de rendimiento **Alerts** del Agente SQL Server contiene contadores de rendimiento que proporcionan información acerca del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bb7ef-103">The SQL Server Agent **Alerts** performance object contains performance counters that report information about SQL Server Agent alerts.</span></span> <span data-ttu-id="bb7ef-104">En la siguiente tabla se enumeran los contadores incluidos en este objeto.</span><span class="sxs-lookup"><span data-stu-id="bb7ef-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="bb7ef-105">La tabla siguiente contiene los contadores **SQLAgent:Alerts** .</span><span class="sxs-lookup"><span data-stu-id="bb7ef-105">The table below contains the **SQLAgent:Alerts** counters.</span></span>  
  
|<span data-ttu-id="bb7ef-106">Nombre</span><span class="sxs-lookup"><span data-stu-id="bb7ef-106">Name</span></span>|<span data-ttu-id="bb7ef-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb7ef-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="bb7ef-108">**Alertas activadas**</span><span class="sxs-lookup"><span data-stu-id="bb7ef-108">**Activated alerts**</span></span>|<span data-ttu-id="bb7ef-109">Este contador indica el número total de alertas que el Agente SQL Server ha activado desde la última vez que se reinició.</span><span class="sxs-lookup"><span data-stu-id="bb7ef-109">This counter reports the total number of alerts that SQL Server Agent has activated since the last time that SQL Server Agent restarted.</span></span>|  
|<span data-ttu-id="bb7ef-110">**Alertas activadas/minuto**</span><span class="sxs-lookup"><span data-stu-id="bb7ef-110">**Alerts activated/minute**</span></span>|<span data-ttu-id="bb7ef-111">Este contador indica el número de alertas que activó el Agente SQL Server en el último minuto.</span><span class="sxs-lookup"><span data-stu-id="bb7ef-111">This counter reports the number of alerts that SQL Server Agent activated within the last minute.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="bb7ef-112">Para usar este objeto del Agente SQL Server, los usuarios deben ser miembros del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="bb7ef-112">To use this SQL Server Agent object, users must be a member of the **sysadmin** fixed server role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb7ef-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb7ef-113">See Also</span></span>  
 <span data-ttu-id="bb7ef-114">[Alerts](../../ssms/agent/alerts.md) </span><span class="sxs-lookup"><span data-stu-id="bb7ef-114">[Alerts](../../ssms/agent/alerts.md) </span></span>  
 <span data-ttu-id="bb7ef-115">[Usar objetos de rendimiento](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="bb7ef-115">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="bb7ef-116">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="bb7ef-116">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
