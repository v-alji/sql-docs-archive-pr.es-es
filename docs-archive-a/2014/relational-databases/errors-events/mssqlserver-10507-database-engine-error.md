---
title: MSSQLSERVER_10507 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10507 (Database Engine error)
ms.assetid: cd83fa81-ac37-4eda-a3c3-17610b051de2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a80e48948c03b370c07742fabbb3cf8eb3e74315
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748813"
---
# <a name="mssqlserver_10507"></a><span data-ttu-id="42274-102">MSSQLSERVER_10507</span><span class="sxs-lookup"><span data-stu-id="42274-102">MSSQLSERVER_10507</span></span>
    
## <a name="details"></a><span data-ttu-id="42274-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="42274-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42274-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="42274-104">Product Name</span></span>|<span data-ttu-id="42274-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="42274-105">SQL Server</span></span>|  
|<span data-ttu-id="42274-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="42274-106">Event ID</span></span>|<span data-ttu-id="42274-107">10507</span><span class="sxs-lookup"><span data-stu-id="42274-107">10507</span></span>|  
|<span data-ttu-id="42274-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="42274-108">Event Source</span></span>|<span data-ttu-id="42274-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="42274-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="42274-110">Componente</span><span class="sxs-lookup"><span data-stu-id="42274-110">Component</span></span>|<span data-ttu-id="42274-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="42274-111">SQLEngine</span></span>|  
|<span data-ttu-id="42274-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="42274-112">Symbolic Name</span></span>|<span data-ttu-id="42274-113">PG_STMT_DOES_NOT_MATCH</span><span class="sxs-lookup"><span data-stu-id="42274-113">PG_STMT_DOES_NOT_MATCH</span></span>|  
|<span data-ttu-id="42274-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="42274-114">Message Text</span></span>|<span data-ttu-id="42274-115">No se puede crear la guía de plan '%.\*ls' porque la instrucción especificada por `@stmt` y `@module_or_batch`, o por `@plan_handle` y `@statement_start_offset`, no coincide con ninguna instrucción del módulo o lote especificado.</span><span class="sxs-lookup"><span data-stu-id="42274-115">Cannot create plan guide '%.\*ls' because the statement specified by `@stmt` and `@module_or_batch`, or by `@plan_handle` and `@statement_start_offset`, does not match any statement in the specified module or batch.</span></span> <span data-ttu-id="42274-116">Modifique los valores para que coincidan con una instrucción del módulo o lote.</span><span class="sxs-lookup"><span data-stu-id="42274-116">Modify the values to match a statement in the module or batch.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="42274-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="42274-117">Explanation</span></span>  
 <span data-ttu-id="42274-118">Una instrucción en el módulo o lote especificado no se pudo hacer coincidir con la instrucción o valor de desplazamiento de instrucción especificados.</span><span class="sxs-lookup"><span data-stu-id="42274-118">A statement in the specified module or batch could not be matched to the specified statement or statement offset value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="42274-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="42274-119">User Action</span></span>  
 <span data-ttu-id="42274-120">Modifique los valores de los parámetros especificados para que coincidan con una instrucción del módulo o lote.</span><span class="sxs-lookup"><span data-stu-id="42274-120">Modify the specified parameter values to match a statement in the module or batch.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42274-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42274-121">See Also</span></span>  
 <span data-ttu-id="42274-122">[Guías de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="42274-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="42274-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="42274-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="42274-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="42274-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
