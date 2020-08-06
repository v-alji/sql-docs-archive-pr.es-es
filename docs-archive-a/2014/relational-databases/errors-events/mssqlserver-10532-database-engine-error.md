---
title: MSSQLSERVER_10532 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10532 (Database Engine error)
ms.assetid: 01da29ee-bf67-433f-8148-587a7e8d1d76
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 26ab34c319eff62737eae337828247fdfd7e901b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749333"
---
# <a name="mssqlserver_10532"></a><span data-ttu-id="03f53-102">MSSQLSERVER_10532</span><span class="sxs-lookup"><span data-stu-id="03f53-102">MSSQLSERVER_10532</span></span>
    
## <a name="details"></a><span data-ttu-id="03f53-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="03f53-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="03f53-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="03f53-104">Product Name</span></span>|<span data-ttu-id="03f53-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="03f53-105">SQL Server</span></span>|  
|<span data-ttu-id="03f53-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="03f53-106">Event ID</span></span>|<span data-ttu-id="03f53-107">10532</span><span class="sxs-lookup"><span data-stu-id="03f53-107">10532</span></span>|  
|<span data-ttu-id="03f53-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="03f53-108">Event Source</span></span>|<span data-ttu-id="03f53-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="03f53-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="03f53-110">Componente</span><span class="sxs-lookup"><span data-stu-id="03f53-110">Component</span></span>|<span data-ttu-id="03f53-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="03f53-111">SQLEngine</span></span>|  
|<span data-ttu-id="03f53-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="03f53-112">Symbolic Name</span></span>|<span data-ttu-id="03f53-113">PG_NO_ELIGIBLE_STMT</span><span class="sxs-lookup"><span data-stu-id="03f53-113">PG_NO_ELIGIBLE_STMT</span></span>|  
|<span data-ttu-id="03f53-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="03f53-114">Message Text</span></span>|<span data-ttu-id="03f53-115">No se puede crear la guía de plan '%.\*ls' porque el lote o módulo especificado por `@plan_handle` no contiene una instrucción válida para una guía de plan.</span><span class="sxs-lookup"><span data-stu-id="03f53-115">Cannot create plan guide '%.\*ls' because the batch or module specified by `@plan_handle` does not contain a statement that is eligible for a plan guide.</span></span> <span data-ttu-id="03f53-116">Especifique un valor distinto para `@plan_handle`.</span><span class="sxs-lookup"><span data-stu-id="03f53-116">Specify a different value for `@plan_handle`.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="03f53-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="03f53-117">Explanation</span></span>  
 <span data-ttu-id="03f53-118">El lote o módulo especificado por `@plan_handle` no contiene una instrucción válida para una guía de plan.</span><span class="sxs-lookup"><span data-stu-id="03f53-118">The batch or module specified by `@plan_handle` does not contain a statement that is eligible for a plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="03f53-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="03f53-119">User Action</span></span>  
 <span data-ttu-id="03f53-120">Especifique un valor distinto para `@plan_handle`.</span><span class="sxs-lookup"><span data-stu-id="03f53-120">Specify a different value for `@plan_handle`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03f53-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="03f53-121">See Also</span></span>  
 <span data-ttu-id="03f53-122">[Guías de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="03f53-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="03f53-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="03f53-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="03f53-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="03f53-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
