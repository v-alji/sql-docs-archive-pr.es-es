---
title: MSSQLSERVER_10519 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10519 (Database Engine error)
ms.assetid: 3be393a1-b186-41ae-afb9-a3d07ff354bb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0ec584649842f787b1de9d2ea6d161aea6970250
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748118"
---
# <a name="mssqlserver_10519"></a><span data-ttu-id="688ca-102">MSSQLSERVER_10519</span><span class="sxs-lookup"><span data-stu-id="688ca-102">MSSQLSERVER_10519</span></span>
    
## <a name="details"></a><span data-ttu-id="688ca-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="688ca-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="688ca-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="688ca-104">Product Name</span></span>|<span data-ttu-id="688ca-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="688ca-105">SQL Server</span></span>|  
|<span data-ttu-id="688ca-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="688ca-106">Event ID</span></span>|<span data-ttu-id="688ca-107">10519</span><span class="sxs-lookup"><span data-stu-id="688ca-107">10519</span></span>|  
|<span data-ttu-id="688ca-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="688ca-108">Event Source</span></span>|<span data-ttu-id="688ca-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="688ca-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="688ca-110">Componente</span><span class="sxs-lookup"><span data-stu-id="688ca-110">Component</span></span>|<span data-ttu-id="688ca-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="688ca-111">SQLEngine</span></span>|  
|<span data-ttu-id="688ca-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="688ca-112">Symbolic Name</span></span>|<span data-ttu-id="688ca-113">PG_INCOMPATIBLE_STMT_AND_HINTS</span><span class="sxs-lookup"><span data-stu-id="688ca-113">PG_INCOMPATIBLE_STMT_AND_HINTS</span></span>|  
|<span data-ttu-id="688ca-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="688ca-114">Message Text</span></span>|<span data-ttu-id="688ca-115">No se puede crear la guía de plan '%.\*ls' porque las sugerencias especificadas en `@hints` no se pueden aplicar a la instrucción especificada por `@stmt` o `@statement_start_offset`.</span><span class="sxs-lookup"><span data-stu-id="688ca-115">Cannot create plan guide '%.\*ls' because the hints specified in `@hints` cannot be applied to the statement specified by either `@stmt` or `@statement_start_offset`.</span></span> <span data-ttu-id="688ca-116">Compruebe que las sugerencias pueden aplicarse a la instrucción.</span><span class="sxs-lookup"><span data-stu-id="688ca-116">Verify that the hints can be applied to the statement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="688ca-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="688ca-117">Explanation</span></span>  
 <span data-ttu-id="688ca-118">Las sugerencias especificadas en `@hints` no se pueden aplicar a la instrucción especificada por `@stmt` o `@statement_start_offset`.</span><span class="sxs-lookup"><span data-stu-id="688ca-118">The hints specified in `@hints` cannot be applied to the statement specified by either `@stmt` or `@statement_start_offset`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="688ca-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="688ca-119">User Action</span></span>  
 <span data-ttu-id="688ca-120">Especifique sugerencias que puedan aplicarse a la instrucción.</span><span class="sxs-lookup"><span data-stu-id="688ca-120">Specify hints that can be applied to the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="688ca-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="688ca-121">See Also</span></span>  
 <span data-ttu-id="688ca-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="688ca-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="688ca-123">[Guías de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="688ca-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="688ca-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="688ca-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
