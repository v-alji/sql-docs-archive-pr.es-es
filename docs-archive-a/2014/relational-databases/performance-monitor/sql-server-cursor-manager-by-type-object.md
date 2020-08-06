---
title: Cursor Manager by Type (objeto de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Cursor Manager by Type object
- SQLServer:Cursor Manager by Type
ms.assetid: d67fbd8a-7554-4a16-96f1-d9ee857a95e3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7bee15aa2917f7b8890e6c1d3f26cc0e210208a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669640"
---
# <a name="sql-server-cursor-manager-by-type-object"></a><span data-ttu-id="25988-102">Cursor Manager by Type (objeto de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="25988-102">SQL Server, Cursor Manager by Type Object</span></span>
  <span data-ttu-id="25988-103">El objeto **SQLServer:Cursor Manager by Type** proporciona contadores para supervisar cursores agrupados por tipo.</span><span class="sxs-lookup"><span data-stu-id="25988-103">The **SQLServer:Cursor Manager by Type** object provides counters to monitor cursors, grouped by type.</span></span>  
  
 <span data-ttu-id="25988-104">En la siguiente tabla se describen los contadores de **Cursor Manager by Type** de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25988-104">This table describes the SQL Server **Cursor Manager by Type** counters.</span></span>  
  
|<span data-ttu-id="25988-105">Contadores de Cursor Manager by Type</span><span class="sxs-lookup"><span data-stu-id="25988-105">Cursor Manager by Type counters</span></span>|<span data-ttu-id="25988-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="25988-106">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="25988-107">**Cursores activos**</span><span class="sxs-lookup"><span data-stu-id="25988-107">**Active cursors**</span></span>|<span data-ttu-id="25988-108">Número de cursores activos.</span><span class="sxs-lookup"><span data-stu-id="25988-108">Number of active cursors.</span></span>|  
|<span data-ttu-id="25988-109">**Frecuencia de aciertos de caché**</span><span class="sxs-lookup"><span data-stu-id="25988-109">**Cache Hit Ratio**</span></span>|<span data-ttu-id="25988-110">Proporción entre los aciertos de caché y las búsquedas.</span><span class="sxs-lookup"><span data-stu-id="25988-110">Ratio between cache hits and lookups.</span></span>|  
|<span data-ttu-id="25988-111">**Recuentos de cursores en caché**</span><span class="sxs-lookup"><span data-stu-id="25988-111">**Cached Cursor Counts**</span></span>|<span data-ttu-id="25988-112">Número de cursores de un tipo determinado en la caché.</span><span class="sxs-lookup"><span data-stu-id="25988-112">Number of cursors of a given type in the cache.</span></span>|  
|<span data-ttu-id="25988-113">**Recuentos de uso de caché de cursor/seg.**</span><span class="sxs-lookup"><span data-stu-id="25988-113">**Cursor Cache Use Count/sec**</span></span>|<span data-ttu-id="25988-114">Número de veces que se ha utilizado cada tipo de cursor en caché.</span><span class="sxs-lookup"><span data-stu-id="25988-114">Times each type of cached cursor has been used.</span></span>|  
|<span data-ttu-id="25988-115">**Uso de memoria de cursores**</span><span class="sxs-lookup"><span data-stu-id="25988-115">**Cursor memory usage**</span></span>|<span data-ttu-id="25988-116">Cantidad de memoria consumida por los cursores en kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="25988-116">Amount of memory consumed by cursors in kilobytes (KB).</span></span>|  
|<span data-ttu-id="25988-117">**Solicitudes de cursor/seg.**</span><span class="sxs-lookup"><span data-stu-id="25988-117">**Cursor Requests/sec**</span></span>|<span data-ttu-id="25988-118">Número de solicitudes de cursor de SQL recibidas por el servidor.</span><span class="sxs-lookup"><span data-stu-id="25988-118">Number of SQL cursor requests received by server.</span></span>|  
|<span data-ttu-id="25988-119">**Uso de tablas de trabajo de cursores**</span><span class="sxs-lookup"><span data-stu-id="25988-119">**Cursor worktable usage**</span></span>|<span data-ttu-id="25988-120">Número de tablas de trabajo utilizadas por los cursores.</span><span class="sxs-lookup"><span data-stu-id="25988-120">Number of worktables used by cursors.</span></span>|  
|<span data-ttu-id="25988-121">**Número de planes de cursor activos**</span><span class="sxs-lookup"><span data-stu-id="25988-121">**Number of active cursor plans**</span></span>|<span data-ttu-id="25988-122">Número de planes de cursor.</span><span class="sxs-lookup"><span data-stu-id="25988-122">Number of cursor plans.</span></span>|  
  
 <span data-ttu-id="25988-123">Cada contador del objeto contiene las instancias siguientes:</span><span class="sxs-lookup"><span data-stu-id="25988-123">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="25988-124">Instancia del administrador de cursor</span><span class="sxs-lookup"><span data-stu-id="25988-124">Cursor Manager instance</span></span>|<span data-ttu-id="25988-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="25988-125">Description</span></span>|  
|-----------------------------|-----------------|  
|<span data-ttu-id="25988-126">**_Total**</span><span class="sxs-lookup"><span data-stu-id="25988-126">**_Total**</span></span>|<span data-ttu-id="25988-127">Información sobre todos los cursores.</span><span class="sxs-lookup"><span data-stu-id="25988-127">Information for all cursors.</span></span>|  
|<span data-ttu-id="25988-128">**API Cursor**</span><span class="sxs-lookup"><span data-stu-id="25988-128">**API Cursor**</span></span>|<span data-ttu-id="25988-129">Solo información del cursor de API.</span><span class="sxs-lookup"><span data-stu-id="25988-129">Only the API cursor information.</span></span>|  
|<span data-ttu-id="25988-130">**TSQL Global Cursor**</span><span class="sxs-lookup"><span data-stu-id="25988-130">**TSQL Global Cursor**</span></span>|<span data-ttu-id="25988-131">Solo información del cursor global de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25988-131">Only the [!INCLUDE[tsql](../../includes/tsql-md.md)] global cursor information.</span></span>|  
|<span data-ttu-id="25988-132">**TSQL Local Cursor**</span><span class="sxs-lookup"><span data-stu-id="25988-132">**TSQL Local Cursor**</span></span>|<span data-ttu-id="25988-133">Solo información del cursor local de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25988-133">Only the [!INCLUDE[tsql](../../includes/tsql-md.md)] local cursor information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25988-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25988-134">See Also</span></span>  
 [<span data-ttu-id="25988-135">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="25988-135">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
