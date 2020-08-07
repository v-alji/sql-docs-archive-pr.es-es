---
title: MSSQLSERVER_10534 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10534 (Database Engine error)
ms.assetid: e65bb118-99d5-4fdb-b1d5-0ec70f0a677b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 793bb0bf5048e30624d9566f65e7c6752bd14386
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745808"
---
# <a name="mssqlserver_10534"></a><span data-ttu-id="53b02-102">MSSQLSERVER_10534</span><span class="sxs-lookup"><span data-stu-id="53b02-102">MSSQLSERVER_10534</span></span>
    
## <a name="details"></a><span data-ttu-id="53b02-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="53b02-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53b02-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="53b02-104">Product Name</span></span>|<span data-ttu-id="53b02-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="53b02-105">SQL Server</span></span>|  
|<span data-ttu-id="53b02-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="53b02-106">Event ID</span></span>|<span data-ttu-id="53b02-107">10534</span><span class="sxs-lookup"><span data-stu-id="53b02-107">10534</span></span>|  
|<span data-ttu-id="53b02-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="53b02-108">Event Source</span></span>|<span data-ttu-id="53b02-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="53b02-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="53b02-110">Componente</span><span class="sxs-lookup"><span data-stu-id="53b02-110">Component</span></span>|<span data-ttu-id="53b02-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="53b02-111">SQLEngine</span></span>|  
|<span data-ttu-id="53b02-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="53b02-112">Symbolic Name</span></span>|<span data-ttu-id="53b02-113">PG_INVALID_PARAMS</span><span class="sxs-lookup"><span data-stu-id="53b02-113">PG_INVALID_PARAMS</span></span>|  
|<span data-ttu-id="53b02-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="53b02-114">Message Text</span></span>|<span data-ttu-id="53b02-115">No se puede crear la guía de plan '%.\*ls' porque el valor especificado para `@params` no es válido.</span><span class="sxs-lookup"><span data-stu-id="53b02-115">Cannot create plan guide '%.\*ls' because the value specified for `@params` is invalid.</span></span> <span data-ttu-id="53b02-116">Especifique el valor con la sintaxis *parameter_name parameter_type*, o especifique NULL.</span><span class="sxs-lookup"><span data-stu-id="53b02-116">Specify the value in the form *parameter_name parameter_type*, or specify NULL.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="53b02-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="53b02-117">Explanation</span></span>  
 <span data-ttu-id="53b02-118">El valor especificado para `@params` no es válido.</span><span class="sxs-lookup"><span data-stu-id="53b02-118">The value specified for `@params` is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="53b02-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="53b02-119">User Action</span></span>  
 <span data-ttu-id="53b02-120">Especifique el valor con la sintaxis *parameter_name parameter_type*, o especifique NULL.</span><span class="sxs-lookup"><span data-stu-id="53b02-120">Specify the value in the form *parameter_name parameter_type*, or specify NULL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53b02-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53b02-121">See Also</span></span>  
 <span data-ttu-id="53b02-122">[Guías de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="53b02-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="53b02-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="53b02-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="53b02-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="53b02-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
