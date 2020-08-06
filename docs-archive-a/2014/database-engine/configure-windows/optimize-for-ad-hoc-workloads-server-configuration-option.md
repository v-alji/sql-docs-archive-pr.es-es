---
title: optimize for ad hoc workloads (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- optimize for ad hoc workloads option
ms.assetid: 0972e028-3a8e-454b-a186-e814a1d431f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b217e48d6e4b0ffa0f687ff170f16d4d77ad17d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744859"
---
# <a name="optimize-for-ad-hoc-workloads-server-configuration-option"></a><span data-ttu-id="295b5-102">optimize for ad hoc workloads (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="295b5-102">optimize for ad hoc workloads Server Configuration Option</span></span>
  <span data-ttu-id="295b5-103">La opción **Optimizar para cargas de trabajo ad hoc** se utiliza para mejorar la eficiencia de la memoria caché del plan para cargas de trabajo que contienen muchos lotes ad hoc de uso único.</span><span class="sxs-lookup"><span data-stu-id="295b5-103">The **optimize for ad hoc workloads** option is used to improve the efficiency of the plan cache for workloads that contain many single use ad hoc batches.</span></span> <span data-ttu-id="295b5-104">Cuando esta opción está establecida en 1, [!INCLUDE[ssDE](../../includes/ssde-md.md)] almacena un pequeño código auxiliar del plan compilado en la memoria caché del plan al compilar un lote por primera vez, en lugar del plan compilado completo.</span><span class="sxs-lookup"><span data-stu-id="295b5-104">When this option is set to 1, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores a small compiled plan stub in the plan cache when a batch is compiled for the first time, instead of the full compiled plan.</span></span> <span data-ttu-id="295b5-105">Esto ayuda a disminuir la demanda de memoria al impedir que la memoria caché del plan se llene de planes compilados que no se reutilizan.</span><span class="sxs-lookup"><span data-stu-id="295b5-105">This helps to relieve memory pressure by not allowing the plan cache to become filled with compiled plans that are not reused.</span></span>  
  
 <span data-ttu-id="295b5-106">El código auxiliar del plan compilado permite que [!INCLUDE[ssDE](../../includes/ssde-md.md)] reconozca que este lote ad hoc se ha compilado antes, pero que solo se ha almacenado un código auxiliar del plan compilado, de modo que cuando se invoca de nuevo este lote (compilado o ejecutado), [!INCLUDE[ssDE](../../includes/ssde-md.md)] compila el lote, quita de la memoria caché del plan el código auxiliar del plan compilado y agrega el plan compilado completo a la memoria caché del plan.</span><span class="sxs-lookup"><span data-stu-id="295b5-106">The compiled plan stub allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to recognize that this ad hoc batch has been compiled before but has only stored a compiled plan stub, so when this batch is invoked (compiled or executed) again, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] compiles the batch, removes the compiled plan stub from the plan cache, and adds the full compiled plan to the plan cache.</span></span>  
  
 <span data-ttu-id="295b5-107">Establecer la opción **Optimizar para cargas de trabajo ad hoc** en 1 afecta solo a los planes nuevos; los planes que ya están en la memoria caché del plan no resultan afectados.</span><span class="sxs-lookup"><span data-stu-id="295b5-107">Setting the **optimize for ad hoc workloads** to 1 affects only new plans; plans that are already in the plan cache are unaffected.</span></span>  
  
 <span data-ttu-id="295b5-108">El código auxiliar del plan compilado es uno de los elementos cacheobjtypes mostrados por la vista de catálogo sys.dm_exec_cached_plans.</span><span class="sxs-lookup"><span data-stu-id="295b5-108">The compiled plan stub is one of the cacheobjtypes displayed by the sys.dm_exec_cached_plans catalog view.</span></span> <span data-ttu-id="295b5-109">Tiene un identificador de sql e identificador del plan único.</span><span class="sxs-lookup"><span data-stu-id="295b5-109">It has a unique sql handle and plan handle.</span></span> <span data-ttu-id="295b5-110">El código auxiliar del plan compilado no tiene un plan de ejecución asociado a él por lo que, al consultar el identificador del plan, no se devolverá un plan de presentación XML.</span><span class="sxs-lookup"><span data-stu-id="295b5-110">The compiled plan stub does not have an execution plan associated with it and querying for the plan handle will not return an XML Showplan.</span></span>  
  
 <span data-ttu-id="295b5-111">La marca de seguimiento 8032 revierte los parámetros de límite de la memoria caché al valor [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] de RTM que en general permite que las memorias caché sean mayores.</span><span class="sxs-lookup"><span data-stu-id="295b5-111">Trace flag 8032 reverts the cache limit parameters to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] RTM setting which in general allows caches to be larger.</span></span> <span data-ttu-id="295b5-112">Use este valor cuando las entradas de caché que se reutilizan con frecuencia no quepan en la memoria caché y cuando la *opción de configuración del servidor Optimizar para cargas de trabajo ad hoc* no haya podido resolver el problema con la caché de planes.</span><span class="sxs-lookup"><span data-stu-id="295b5-112">Use this setting when frequently reused cache entries do not fit into the cache and when the *optimize for ad hoc workloads Server Configuration Option* has failed to resolve the problem with plan cache.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="295b5-113">La marca de seguimiento 8032 puede ocasionar la degradación del rendimiento si las memorias caché grandes suponen que haya menos memoria disponible para otros consumidores de memoria, como el grupo de búferes.</span><span class="sxs-lookup"><span data-stu-id="295b5-113">Trace flag 8032 can cause poor performance if large caches make less memory available for other memory consumers, such as the buffer pool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="295b5-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="295b5-114">See Also</span></span>  
 <span data-ttu-id="295b5-115">[sys.dm_exec_cached_plans &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-cached-plans-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="295b5-115">[sys.dm_exec_cached_plans &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-cached-plans-transact-sql) </span></span>  
 [<span data-ttu-id="295b5-116">Opciones de configuración de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="295b5-116">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
