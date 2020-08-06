---
title: SQL Server, nodo de memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 55b28ba9-b6d5-4ea9-8103-db8a72f42982
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d5bbc3f581ea9ececeb7d55a614ef27c3c72de7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677036"
---
# <a name="sql-server-memory-node"></a><span data-ttu-id="15f70-102">SQL Server, Nodo de memoria</span><span class="sxs-lookup"><span data-stu-id="15f70-102">SQL Server, Memory Node</span></span>
  <span data-ttu-id="15f70-103">El objeto **Nodo de memoria** de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proporciona contadores para supervisar la utilización de la memoria de servidor en los nodos NUMA.</span><span class="sxs-lookup"><span data-stu-id="15f70-103">The **Memory Node** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor server memory usage on NUMA nodes.</span></span>  
  
## <a name="memory-node-counters"></a><span data-ttu-id="15f70-104">Contadores del Nodo de memoria</span><span class="sxs-lookup"><span data-stu-id="15f70-104">Memory Node Counters</span></span>  
 <span data-ttu-id="15f70-105">En esta tabla se describen los contadores de **Nodo de memoria** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15f70-105">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Memory Node** counters.</span></span>  
  
|<span data-ttu-id="15f70-106">Contadores de Memory Manager de SQL Server</span><span class="sxs-lookup"><span data-stu-id="15f70-106">SQL Server Memory Manager counters</span></span>|<span data-ttu-id="15f70-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="15f70-107">Description</span></span>|  
|----------------------------------------|-----------------|  
|<span data-ttu-id="15f70-108">**Memoria del nodo de base de datos (KB)**</span><span class="sxs-lookup"><span data-stu-id="15f70-108">**Database Node Memory (KB)**</span></span>|<span data-ttu-id="15f70-109">Especifica la cantidad de memoria que el servidor usa actualmente en este nodo para las páginas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="15f70-109">Specifies the amount of memory the server is currently using on this node for database pages.</span></span>|  
|<span data-ttu-id="15f70-110">**Memoria disponible del nodo libre (KB)**</span><span class="sxs-lookup"><span data-stu-id="15f70-110">**Free Node Memory (KB)**</span></span>|<span data-ttu-id="15f70-111">Especifica la cantidad de memoria que el servidor no utiliza en este nodo.</span><span class="sxs-lookup"><span data-stu-id="15f70-111">Specifies the amount of memory the server is not using on this node.</span></span>|  
|<span data-ttu-id="15f70-112">**Memoria del nodo externa (KB)**</span><span class="sxs-lookup"><span data-stu-id="15f70-112">**Foreign Node Memory (KB)**</span></span>|<span data-ttu-id="15f70-113">Especifica la cantidad de memoria local que no es NUMA en este nodo.</span><span class="sxs-lookup"><span data-stu-id="15f70-113">Specifies the amount of non NUMA-local memory on this node.</span></span>|  
|<span data-ttu-id="15f70-114">**Nodo de memoria robada (KB)**</span><span class="sxs-lookup"><span data-stu-id="15f70-114">**Stolen Memory Node (KB)**</span></span>|<span data-ttu-id="15f70-115">Especifica la cantidad de memoria que el servidor usa en este nodo para otro fin distinto a las páginas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="15f70-115">Specifies the amount of memory the server is using on this node for purposes other than database pages.</span></span>|  
|<span data-ttu-id="15f70-116">**Memoria del nodo de destino**</span><span class="sxs-lookup"><span data-stu-id="15f70-116">**Target Node Memory**</span></span>|<span data-ttu-id="15f70-117">Especifica la cantidad de memoria ideal para este nodo.</span><span class="sxs-lookup"><span data-stu-id="15f70-117">Specifies the ideal amount of memory for this node.</span></span>|  
|<span data-ttu-id="15f70-118">**Memoria total del nodo**</span><span class="sxs-lookup"><span data-stu-id="15f70-118">**Total Node Memory**</span></span>|<span data-ttu-id="15f70-119">Indica la cantidad de memoria total que el servidor ha confirmado en este nodo.</span><span class="sxs-lookup"><span data-stu-id="15f70-119">Indicates the total amount of memory the server has committed on this node.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15f70-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15f70-120">See Also</span></span>  
 <span data-ttu-id="15f70-121">[Supervisar el uso de recursos &#40;Monitor de sistema&#41;](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="15f70-121">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="15f70-122">[Buffer Manager (objeto de SQL Server)](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="15f70-122">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="15f70-123">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="15f70-123">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql)  
  
  
