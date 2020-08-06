---
title: SQL Server:Buffer Node | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Buffer Node
- Buffer Node object
ms.assetid: fd3f9f0f-7c38-4cfd-a0c5-ee93dd52d9a5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 14659e4c1191e2260bccdbcd612f510770913629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675810"
---
# <a name="sql-serverbuffer-node"></a><span data-ttu-id="0f514-102">SQL Server:Buffer Node</span><span class="sxs-lookup"><span data-stu-id="0f514-102">SQL Server:Buffer Node</span></span>
  <span data-ttu-id="0f514-103">El objeto **Buffer Node** proporciona contadores que complementan a los contadores proporcionados por el objeto **Buffer Manager** .</span><span class="sxs-lookup"><span data-stu-id="0f514-103">The **Buffer Node** object provides counters that complement counters provided by the **Buffer Manager** object.</span></span> <span data-ttu-id="0f514-104">Este objeto permite supervisar la distribución de páginas del grupo de búferes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para cada nodo de acceso no uniforme a memoria (NUMA).</span><span class="sxs-lookup"><span data-stu-id="0f514-104">It allows you to monitor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] buffer pool page distribution for each non-uniform memory access (NUMA) node.</span></span> <span data-ttu-id="0f514-105">Existe una instancia del objeto **Buffer Node** para cada nodo NUMA que está en uso.</span><span class="sxs-lookup"><span data-stu-id="0f514-105">There is an instance of the **Buffer Node** object for each NUMA node in use.</span></span> <span data-ttu-id="0f514-106">En la arquitectura no NUMA, habrá una sola instancia del objeto **Buffer Node** .</span><span class="sxs-lookup"><span data-stu-id="0f514-106">On non-NUMA architecture, there will be a single instance of the **Buffer Node** object.</span></span>  
  
## <a name="buffer-node-performance-objects"></a><span data-ttu-id="0f514-107">Objetos de rendimiento Buffer Node</span><span class="sxs-lookup"><span data-stu-id="0f514-107">Buffer Node Performance Objects</span></span>  
 <span data-ttu-id="0f514-108">En esta tabla se describen los objetos de rendimiento **Buffer Node** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f514-108">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Buffer Node** performance objects.</span></span>  
  
|<span data-ttu-id="0f514-109">Contadores de SQLServer:Buffer Node</span><span class="sxs-lookup"><span data-stu-id="0f514-109">SQL Server Buffer Node counters</span></span>|<span data-ttu-id="0f514-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f514-110">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="0f514-111">**Páginas de base de datos**</span><span class="sxs-lookup"><span data-stu-id="0f514-111">**Database pages**</span></span>|<span data-ttu-id="0f514-112">Indica el número de páginas del grupo de búferes de este nodo con contenido de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0f514-112">Indicates the number of pages in the buffer pool on this node with database content.</span></span>|  
|<span data-ttu-id="0f514-113">**Duración prevista de la página**</span><span class="sxs-lookup"><span data-stu-id="0f514-113">**Page life expectancy**</span></span>|<span data-ttu-id="0f514-114">Indica el número mínimo de segundos que una página permanecerá en el grupo de búferes de este nodo sin referencias.</span><span class="sxs-lookup"><span data-stu-id="0f514-114">Indicates the minimum number of seconds a page will stay in the buffer pool on this node without references.</span></span>|  
|<span data-ttu-id="0f514-115">**Búsquedas de páginas de nodos locales por segundo**</span><span class="sxs-lookup"><span data-stu-id="0f514-115">**Local Node page lookups/sec**</span></span>|<span data-ttu-id="0f514-116">Indica el número de solicitudes de búsqueda de este nodo que se satisfacen desde este mismo nodo.</span><span class="sxs-lookup"><span data-stu-id="0f514-116">Indicates the number of lookup requests from this node which were satisfied from this node.</span></span>|  
|<span data-ttu-id="0f514-117">**Búsquedas de páginas de nodos remotos por segundo**</span><span class="sxs-lookup"><span data-stu-id="0f514-117">**Remote Note page lookups/sec**</span></span>|<span data-ttu-id="0f514-118">Indica el número de solicitudes de búsqueda de este nodo que se satisfacen desde otros nodos.</span><span class="sxs-lookup"><span data-stu-id="0f514-118">Indicates the number of lookup requests from this node which were satisfied from other nodes.</span></span>|  
  
 <span data-ttu-id="0f514-119">Si SQL Server se ejecuta en un hardware que no es de NUMA, los contadores de los objetos **Buffer Node** y **Buffer Manager** deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="0f514-119">If SQL Server is running on non-NUMA hardware, the counters of **Buffer Node** and **Buffer Manager** objects should match.</span></span>  
  
 <span data-ttu-id="0f514-120">En hardware de NUMA, las sumas de todos los contadores respectivos de **Buffer Node** deben coincidir con sus equivalentes de **Buffer Manager**.</span><span class="sxs-lookup"><span data-stu-id="0f514-120">On NUMA hardware, sums of respective counters of all **Buffer Nodes** should match their counterparts of **Buffer Manager**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f514-121">Es posible que las sumas y los valores de contador no coincidan debido precisamente a la naturaleza dinámica de los contadores y la precisión del muestreo.</span><span class="sxs-lookup"><span data-stu-id="0f514-121">The counter values and sums may not match precisely due to the dynamic nature of the counters and the sampling accuracy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f514-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0f514-122">See Also</span></span>  
 <span data-ttu-id="0f514-123">[Buffer Manager (objeto de SQL Server)](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="0f514-123">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 <span data-ttu-id="0f514-124">[Opciones de configuración de memoria del servidor](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="0f514-124">[Server Memory Server Configuration Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="0f514-125">[Supervisar el uso de recursos &#40;Monitor de sistema&#41;](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="0f514-125">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 [<span data-ttu-id="0f514-126">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0f514-126">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql)  
  
  
