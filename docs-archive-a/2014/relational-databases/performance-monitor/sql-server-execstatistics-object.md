---
title: ExecStatistics (objeto de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:ExecStatistics
- ExecStatistics object
ms.assetid: 4f8557a8-345f-4622-a8a5-763a0388ad94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d1a50c97add4708a58b9edc45fd49982b97a51ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669630"
---
# <a name="sql-server-execstatistics-object"></a><span data-ttu-id="e5d60-102">ExecStatistics (objeto de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e5d60-102">SQL Server, ExecStatistics Object</span></span>
  <span data-ttu-id="e5d60-103">El objeto **SQLServer:ExecStatistics** de Microsoft SQL Server proporciona contadores para supervisar diversas ejecuciones.</span><span class="sxs-lookup"><span data-stu-id="e5d60-103">The **SQLServer:ExecStatistics** object in Microsoft SQL Server provides counters to monitor various executions.</span></span>  
  
 <span data-ttu-id="e5d60-104">En esta tabla se describen los contadores de **Exec Statistics** de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e5d60-104">This table describes the SQL Server **Exec Statistics** counters.</span></span>  
  
|<span data-ttu-id="e5d60-105">Contadores de Exec Statistics de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e5d60-105">SQL Server Exec Statistics counters</span></span>|<span data-ttu-id="e5d60-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5d60-106">Description</span></span>|  
|-----------------------------------------|-----------------|  
|<span data-ttu-id="e5d60-107">**Consulta distribuida**</span><span class="sxs-lookup"><span data-stu-id="e5d60-107">**Distributed Query**</span></span>|<span data-ttu-id="e5d60-108">Estadísticas relacionadas con la ejecución de consultas distribuidas.</span><span class="sxs-lookup"><span data-stu-id="e5d60-108">Statistics relevant to execution of distributed queries.</span></span>|  
|<span data-ttu-id="e5d60-109">**Llamadas DTC**</span><span class="sxs-lookup"><span data-stu-id="e5d60-109">**DTC calls**</span></span>|<span data-ttu-id="e5d60-110">Estadísticas relacionadas con la ejecución de llamadas DTC.</span><span class="sxs-lookup"><span data-stu-id="e5d60-110">Statistics relevant to execution of DTC calls.</span></span>|  
|<span data-ttu-id="e5d60-111">**Procedimientos extendidos**</span><span class="sxs-lookup"><span data-stu-id="e5d60-111">**Extended Procedures**</span></span>|<span data-ttu-id="e5d60-112">Estadísticas relacionadas con la ejecución de procedimientos extendidos.</span><span class="sxs-lookup"><span data-stu-id="e5d60-112">Statistics relevant to execution of extended procedures.</span></span>|  
|<span data-ttu-id="e5d60-113">**Llamadas OLEDB**</span><span class="sxs-lookup"><span data-stu-id="e5d60-113">**OLEDB calls**</span></span>|<span data-ttu-id="e5d60-114">Estadísticas relacionadas con la ejecución de llamadas OLEDB.</span><span class="sxs-lookup"><span data-stu-id="e5d60-114">Statistics relevant to execution of OLEDB calls.</span></span>|  
  
 <span data-ttu-id="e5d60-115">Cada contador del objeto contiene las instancias siguientes:</span><span class="sxs-lookup"><span data-stu-id="e5d60-115">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="e5d60-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5d60-116">Item</span></span>|<span data-ttu-id="e5d60-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5d60-117">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="e5d60-118">**Tiempo medio de ejecución (ms)**</span><span class="sxs-lookup"><span data-stu-id="e5d60-118">**Average execution time (ms)**</span></span>|<span data-ttu-id="e5d60-119">Tiempo medio de ejecución del tipo de ejecución seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e5d60-119">Average execution time of the selected type of execution.</span></span>|  
|<span data-ttu-id="e5d60-120">**Tiempo de ejecución acumulado (ms) por segundo**</span><span class="sxs-lookup"><span data-stu-id="e5d60-120">**Cumulative execution time (ms) per second**</span></span>|<span data-ttu-id="e5d60-121">Tiempo de ejecución acumulado por segundo del tipo de ejecución seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e5d60-121">Aggregated execution time per second, of the selected type of execution.</span></span>|  
|<span data-ttu-id="e5d60-122">**Ejecuciones en curso**</span><span class="sxs-lookup"><span data-stu-id="e5d60-122">**Execs in progress**</span></span>|<span data-ttu-id="e5d60-123">Número de ejecuciones en curso del tipo de ejecución seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e5d60-123">Number of execs in progress of the selected type of execution.</span></span>|  
|<span data-ttu-id="e5d60-124">**Ejecuciones iniciadas por segundo**</span><span class="sxs-lookup"><span data-stu-id="e5d60-124">**Exec started per second**</span></span>|<span data-ttu-id="e5d60-125">Número de ejecuciones iniciadas por segundo del tipo de ejecución seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e5d60-125">Number of exes started per second of the selected type of execution.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5d60-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5d60-126">See Also</span></span>  
 [<span data-ttu-id="e5d60-127">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="e5d60-127">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
