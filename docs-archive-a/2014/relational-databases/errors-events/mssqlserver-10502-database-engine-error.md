---
title: MSSQLSERVER_10502 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10502 (Database Engine error)
ms.assetid: 26d9b64d-4299-4b55-92d0-0a32a3688c0a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: eeec3a3adf318cadc96501938f8a5565f1c07670
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663008"
---
# <a name="mssqlserver_10502"></a><span data-ttu-id="ab1ce-102">MSSQLSERVER_10502</span><span class="sxs-lookup"><span data-stu-id="ab1ce-102">MSSQLSERVER_10502</span></span>
    
## <a name="details"></a><span data-ttu-id="ab1ce-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ab1ce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab1ce-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="ab1ce-104">Product Name</span></span>|<span data-ttu-id="ab1ce-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ab1ce-105">SQL Server</span></span>|  
|<span data-ttu-id="ab1ce-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab1ce-106">Event ID</span></span>|<span data-ttu-id="ab1ce-107">10502</span><span class="sxs-lookup"><span data-stu-id="ab1ce-107">10502</span></span>|  
|<span data-ttu-id="ab1ce-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="ab1ce-108">Event Source</span></span>|<span data-ttu-id="ab1ce-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ab1ce-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ab1ce-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ab1ce-110">Component</span></span>|<span data-ttu-id="ab1ce-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ab1ce-111">SQLEngine</span></span>|  
|<span data-ttu-id="ab1ce-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ab1ce-112">Symbolic Name</span></span>|<span data-ttu-id="ab1ce-113">PG_DUP_FOUND</span><span class="sxs-lookup"><span data-stu-id="ab1ce-113">PG_DUP_FOUND</span></span>|  
|<span data-ttu-id="ab1ce-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ab1ce-114">Message Text</span></span>|<span data-ttu-id="ab1ce-115">No se puede crear la guía de plan '%.\*ls' porque la instrucción especificada por @stmt y @module_or_batch, o por @plan_handle y @statement_start_offset, coincide con la guía de plan '%.\*ls' existente en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-115">Cannot create plan guide '%.\*ls' because the statement specified by @stmt and @module_or_batch, or by @plan_handle and @statement_start_offset, matches the existing plan guide '%.\*ls' in the database.</span></span> <span data-ttu-id="ab1ce-116">Quite la guía de plan existente antes de crear la nueva.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-116">Drop the existing plan guide before creating the new plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ab1ce-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="ab1ce-117">Explanation</span></span>  
 <span data-ttu-id="ab1ce-118">Existe una guía de plan para la instrucción especificada.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-118">A plan guide exists for the specified statement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ab1ce-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ab1ce-119">User Action</span></span>  
 <span data-ttu-id="ab1ce-120">Quite la guía de plan existente antes de crear la nueva.</span><span class="sxs-lookup"><span data-stu-id="ab1ce-120">Drop the existing plan guide before creating the new plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab1ce-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab1ce-121">See Also</span></span>  
 <span data-ttu-id="ab1ce-122">[Guías de plan](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="ab1ce-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="ab1ce-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ab1ce-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="ab1ce-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ab1ce-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
