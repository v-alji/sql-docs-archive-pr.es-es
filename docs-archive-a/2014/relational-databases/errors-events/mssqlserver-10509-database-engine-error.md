---
title: MSSQLSERVER_10509 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10509 (Database Engine error)
ms.assetid: e9dd5357-ee3d-420a-9a89-d12ab5404e73
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73194c7da553bf27acb78d8c4e7d71bc93f457d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749958"
---
# <a name="mssqlserver_10509"></a><span data-ttu-id="d42bd-102">MSSQLSERVER_10509</span><span class="sxs-lookup"><span data-stu-id="d42bd-102">MSSQLSERVER_10509</span></span>
    
## <a name="details"></a><span data-ttu-id="d42bd-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d42bd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d42bd-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="d42bd-104">Product Name</span></span>|<span data-ttu-id="d42bd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d42bd-105">SQL Server</span></span>|  
|<span data-ttu-id="d42bd-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d42bd-106">Event ID</span></span>|<span data-ttu-id="d42bd-107">10509</span><span class="sxs-lookup"><span data-stu-id="d42bd-107">10509</span></span>|  
|<span data-ttu-id="d42bd-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="d42bd-108">Event Source</span></span>|<span data-ttu-id="d42bd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d42bd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d42bd-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d42bd-110">Component</span></span>|<span data-ttu-id="d42bd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d42bd-111">SQLEngine</span></span>|  
|<span data-ttu-id="d42bd-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d42bd-112">Symbolic Name</span></span>|<span data-ttu-id="d42bd-113">PG_INVALID_STMT</span><span class="sxs-lookup"><span data-stu-id="d42bd-113">PG_INVALID_STMT</span></span>|  
|<span data-ttu-id="d42bd-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d42bd-114">Message Text</span></span>|<span data-ttu-id="d42bd-115">No se puede crear la guía de plan '%.\*ls' porque la instrucción especificada por `@stmt` o `@statement_start_offset` contiene un error de sintaxis o es ilegible para una guía de plan.</span><span class="sxs-lookup"><span data-stu-id="d42bd-115">Cannot create plan guide '%.\*ls' because the statement specified by `@stmt` or `@statement_start_offset` either contains a syntax error or is ineligible for use in a plan guide.</span></span> <span data-ttu-id="d42bd-116">Especifique una sola instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] válida o una posición inicial válida de la instrucción en el lote.</span><span class="sxs-lookup"><span data-stu-id="d42bd-116">Provide a single valid [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a valid starting position of the statement within the batch.</span></span> <span data-ttu-id="d42bd-117">Para obtener una posición inicial válida, consulte la columna statement_start_offset de la función de administración dinámica sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="d42bd-117">To obtain a valid starting position, query the statement_start_offset column in the sys.dm_exec_query_stats dynamic management function.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d42bd-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="d42bd-118">Explanation</span></span>  
 <span data-ttu-id="d42bd-119">La instrucción especificada por `@stmt` o `@statement_start_offset` contiene un error de sintaxis o es ilegible para una guía de plan.</span><span class="sxs-lookup"><span data-stu-id="d42bd-119">The statement specified by `@stmt` or `@statement_start_offset` either contains a syntax error or is ineligible for use in a plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d42bd-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d42bd-120">User Action</span></span>  
 <span data-ttu-id="d42bd-121">Especifique una sola instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] válida o una posición inicial válida de la instrucción en el lote.</span><span class="sxs-lookup"><span data-stu-id="d42bd-121">Provide a single valid [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a valid starting position of the statement within the batch.</span></span> <span data-ttu-id="d42bd-122">Para obtener una posición inicial válida, consulte la columna statement_start_offset de la función de administración dinámica sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="d42bd-122">To obtain a valid starting position, query the statement_start_offset column in the sys.dm_exec_query_stats dynamic management function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d42bd-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d42bd-123">See Also</span></span>  
 <span data-ttu-id="d42bd-124">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d42bd-124">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="d42bd-125">[Guías de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="d42bd-125">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="d42bd-126">[Sys. dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d42bd-126">[sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) </span></span>  
 [<span data-ttu-id="d42bd-127">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d42bd-127">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
