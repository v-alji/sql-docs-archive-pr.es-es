---
title: MSSQLSERVER_10536 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10536 (Database Engine error)
ms.assetid: 9f97b41f-0ef8-4ad2-aec0-906a5d7522ba
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 00d08f4555f38b61661a917ba94c023f9dd6c4a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747021"
---
# <a name="mssqlserver_10536"></a><span data-ttu-id="b5f7d-102">MSSQLSERVER_10536</span><span class="sxs-lookup"><span data-stu-id="b5f7d-102">MSSQLSERVER_10536</span></span>
    
## <a name="details"></a><span data-ttu-id="b5f7d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b5f7d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b5f7d-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="b5f7d-104">Product Name</span></span>|<span data-ttu-id="b5f7d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b5f7d-105">SQL Server</span></span>|  
|<span data-ttu-id="b5f7d-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b5f7d-106">Event ID</span></span>|<span data-ttu-id="b5f7d-107">10536</span><span class="sxs-lookup"><span data-stu-id="b5f7d-107">10536</span></span>|  
|<span data-ttu-id="b5f7d-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="b5f7d-108">Event Source</span></span>|<span data-ttu-id="b5f7d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b5f7d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b5f7d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b5f7d-110">Component</span></span>|<span data-ttu-id="b5f7d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b5f7d-111">SQLEngine</span></span>|  
|<span data-ttu-id="b5f7d-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b5f7d-112">Symbolic Name</span></span>|<span data-ttu-id="b5f7d-113">PG_TOO_MANY_STMTS</span><span class="sxs-lookup"><span data-stu-id="b5f7d-113">PG_TOO_MANY_STMTS</span></span>|  
|<span data-ttu-id="b5f7d-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b5f7d-114">Message Text</span></span>|<span data-ttu-id="b5f7d-115">No se puede crear la Guía de plan '%.\*ls' porque el lote o módulo correspondiente al especificado `@plan_handle` contiene más de 1000 instrucciones válidas.</span><span class="sxs-lookup"><span data-stu-id="b5f7d-115">Cannot create plan guide '%.\*ls' because the batch or module corresponding to the specified `@plan_handle` contains more than 1000 eligible statements.</span></span> <span data-ttu-id="b5f7d-116">Cree una guía de plan para cada instrucción en el lote o módulo especificando un valor `statement_start_offset` para cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="b5f7d-116">Create a plan guide for each statement in the batch or module by specifying a `statement_start_offset` value for each statement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b5f7d-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="b5f7d-117">Explanation</span></span>  
 <span data-ttu-id="b5f7d-118">El lote o módulo correspondiente al identificador `@plan_handle` especificado contiene más de 1000 instrucciones válidas.</span><span class="sxs-lookup"><span data-stu-id="b5f7d-118">The batch or module corresponding to the specified `@plan_handle` contains more than 1000 eligible statements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b5f7d-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b5f7d-119">User Action</span></span>  
 <span data-ttu-id="b5f7d-120">Cree una guía de plan para cada instrucción en el lote o módulo especificando un valor `statement_start_offset` para cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="b5f7d-120">Create a plan guide for each statement in the batch or module by specifying a `statement_start_offset` value for each statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5f7d-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5f7d-121">See Also</span></span>  
 <span data-ttu-id="b5f7d-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b5f7d-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="b5f7d-123">[Guías de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="b5f7d-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="b5f7d-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b5f7d-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
